## JavaScript

> 需要注意的是，此实现并没有发到 `npm` 上，需使用方自行复制

### 使用实例

#### SDK Token

```javascript
const  { sdkToken, TokenPrefix } = require("./index");

// 生成 sdk token
const netlessSDKToken = sdkToken(
    "netless ak",
    "netless sk",
    1000 * 60 * 10, // token 有效时间 (10分钟)，为 0 时，即永不过期。单位毫秒
    {
        role: TokenRole.Admin // 可以选择 TokenRole.Reader / TokenRole.Writer
    }
);
```

#### Room Token

```javascript
const  { roomToken, TokenPrefix } = require("./src/index");

// 生成 room token
const netlessRoomToken = roomToken(
    "netless ak",
    "netless sk",
    1000 * 60 * 10, // token 有效时间 (10分钟)，为 0 时，即永不过期。单位毫秒
    {
        role: TokenRole.Reader, // 可以选择 TokenRole.Admin / TokenRole.Writer
        uuid: "房间的 UUID"
    }
);
```

#### Task Token

```javascript
const  { taskToken, TokenPrefix } = require("./src/index");


// 生成 task token
const netlessTaskToken = taskToken(
    "netless ak",
    "netless sk",
    1000 * 60 * 10, // token 有效时间 (10分钟)，为 0 时，即永不过期。单位毫秒
    {
        role: TokenRole.Writer,  // 可以选择 TokenRole.Admin / TokenRole.Reader
        uuid: "房间的 UUID"
    }
);
```
