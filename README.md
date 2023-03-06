# dbComm

All interactions with DB

## Schema for rawinfo

```
rawinfo {
    type?: string,
    author: string,
    content: string,
    user_mentions?: Array<string>,
    role_mentions?: Array<string>,
    reactions?: Array<string>,
    replied_user?: string,
    channelId: Snowflake,
    messageId: Snowflake,(unique)
    threadId: Snowflake,
    thread: string,
    datetime: string (format: "YYYY-MM-DD")
}
```

### Schema for user

```
User {
    discordId: Snowflake,
    username?: string,
    discriminator?: string,
    avatar?: string,
    bot?: boolean,
    system?: boolean,
    mfa_enabled?: boolean,
    banner?: string,
    accent_color?: number
    locale?: string,
    verified?: boolean
    email?: string,
    flags?: number,
    premium_type?: number,
    public_flags?: number,
}
```

### Schema for heatmap

```

HeatMap {
    date?: string,(format: "YYYY-MM-DD")
    thr_messages: Array<number>,
    lone_messages: Array<number>,
    replier: Array<number>,
    replier_accounts: Array<objects> [{account: "account name", count: "count of reply"}],
    replied: Array<number>,
    mentioner: Array<number>,
    mentioner_accounts: Array<objects> [{account: "account name", count: "count of reply"}],
    mentioned: Array<number>,
    reacter: Array<number>,
    reacter_accounts: Array<objects> [{account: "account name", count: "count of reply"}],
    reacted: Array<number>,
    channelId: string,
    account: string
}
```

### Schema for channels

```

Channels {
    channel: string,
    channelId: Snowflake,
    last_update: Date
}
```


### Schema for token

```
Token {
    token: string,
    user: Snowflake,
    type: string,
    expires: Date,
    blacklisted?: boolean
}
```

### Schema for guild

```
Guild {
    guildId: Snowflake,
    user: Snowflake,
    name?: string,
    selectedChannels?: [
        {
            channelId: Snowflake,
            channelName?: string
        }
    ],
    period?: Date,
    connectedAt?: Date,
    isInProgress?: Boolean
    isDisconnected?: Boolean
}
```
