FROM node:18.13.0-alpine3.17

ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"

COPY . /next
WORKDIR /next

RUN corepack enable
RUN --mount=type=cache,id=pnpm,target=/pnpm/store pnpm install --frozen-lockfile
RUN pnpm run build

COPY . ./next

EXPOSE 3000

CMD ["pnpm", "start"]
