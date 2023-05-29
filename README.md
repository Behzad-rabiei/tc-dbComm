# dbComm

All interactions with DB

[![Maintainability](https://api.codeclimate.com/v1/badges/52d516c2ad7c262adb37/maintainability)](https://codeclimate.com/github/RnDAO/tc-dbComm/maintainability)
[![Test Coverage](https://api.codeclimate.com/v1/badges/52d516c2ad7c262adb37/test_coverage)](https://codeclimate.com/github/RnDAO/tc-dbComm/test_coverage)


## Schema for rawinfo

```
rawinfo {
  type: number,
  author: Snowflake,
  content: string,
  createdDate: Date,
  user_mentions: Array<Snowflake>,
  role_mentions: Array<Snowflake>,
  reactions: Array<Snowflake>,
  replied_user: Snowflake | null | undefined,
  messageId: Snowflake,
  channelId: Snowflake,
  channelName: string | null,
  threadId: Snowflake | null,
  threadName: string | null,
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
    replied_per_acc: Array<objects> [{account: "account name", count: "count of reply"}],
    replied: Array<number>,
    mentioner: Array<number>,
    mentioner_per_acc: Array<objects> [{account: "account name", count: "count of mention"}],
    mentioned: Array<number>,
    reacter: Array<number>,
    reacted_per_acc: Array<objects> [{account: "account name", count: "count of reaction"}],
    reacted: Array<number>,
    channelId: string,
    account_name: string
}
```

### Schema for guildMembers

```
GuildMember {
  discordId: Snowflake,
  username: string,
  avatar?: string | null,
  roles: Snowflake[],
  joinedAt: Date | null,
  isBot?: boolean,
  discriminator: string
}

```

### Schema for memberactivities

```

memberactivities {
    date: Date,
    all_active: Array<string>,
    all_consistent: Array<string>,
    all_vital: Array<string>,
    all_connected: Array<string>,
    all_paused: Array<string>,
    all_new_disengaged: Array<string>,
    all_disengaged: Array<string>,
    all_unpaused: Array<string>,
    all_returned: Array<string>,
    all_new_active: Array<string>,
    all_still_active: Array<string>,
    all_dropped: Array<string>,
    all_joined: Array<string>,
    all_disengaged_were_newly_active: Array<string>,
    all_disengaged_were_consistenly_active: Array<string>,
    all_disengaged_were_vital: Array<string>,
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
    connectedAt?: Date,
    isInProgress?: Boolean,
    isDisconnected?: Boolean,
    icon?: string,
    selectedChannels?: Array<objects> [
        {
            channelId: Snowflake,
            channelName?: string
        }
    ],
    period?: Date,
    aciton: Array<number>,
    window: Array<number>
}
```
