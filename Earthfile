VERSION 0.6
FROM earthly/dind

deps:
    ARG SUPABASE_VERSION=1.16.3
    RUN wget -q -O /tmp/supabase_${SUPABASE_VERSION}_linux_amd64.apk https://github.com/supabase/cli/releases/download/v${SUPABASE_VERSION}/supabase_${SUPABASE_VERSION}_linux_amd64.apk \
        && apk add --allow-untrusted /tmp/supabase_${SUPABASE_VERSION}_linux_amd64.apk \
        && rm /tmp/supabase_${SUPABASE_VERSION}_linux_amd64.apk
    COPY supabase/config.toml supabase/config.toml
    WITH DOCKER
        RUN supabase start
    END
