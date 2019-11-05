# 3Box Plugins

The 3Box Plugins module is an experiment to create an plugin system for 3Box.

Simplifying the steps required to add decentralized authentication, storage and messaging.

## Resources

Before getting started with this repo, please reference the 3Box documentation and libraries.

- https://docs.3box.io/
- https://www.npmjs.com/package/3box

## Major Packages

- 3Box UI State (3box-ui-state)
- 3Box UI System (3box-ui-system)
- 3Box UI System Render (3box-ui-system-render)
- 3Box UI Profiles (3box-ui-profiles)
- 3Box UI Profiles Stateless (3box-ui-profiles-stateless)

## Developer Setup

Install: `yarn`

Watch: `yarn watch`

Run: `cd packages/apps/dapp ; yarn start`

More developer documentation coming soon.

## 3Box UI State

The Context interface is a great place to to start understanding the core 3box-ui-state state system.

Context Example

```
enable: () => { },
login: () => { },
logout: () => { },
addRequest: () => { },
confirmRequest: () => { },
confirmAllRequests: () => { },
openSpace: () => { },
listSpaces: () => { },
subscribedThreads: () => { },
getThread: () => { },
getThreadByAddress: () => { },
getConfig: () => { },
getVerifiedAccounts: () => { },
joinThread: () => { },
joinThreadByAddress: () => { },
threadPost: () => { },
threadPostDelete: () => { },
threadListen: () => { },
threadAddModerator: () => { },
threadAddMember: () => { },
```

The full context includes a of initial state defaults and empty functions which will be replace via the initialized action types.

## 3Box UI System

Below is small sample of components to help enable rapid development.

### Login

```js
import {Login} from '@kames/3box-system';
const Component = props => <Login />;
```

## Access Control

### AccessProfile

```js
import { AccessProfile } from '@kames/3box-system'
const Component = props =>
<AccessProfile>
  <MyFormComponent />
</AccessThread>
```

### AccessSpace

```js
import { AccessSpace } from '@kames/3box-system'
const Component = props =>
<AccessSpace space='web3'>
  <MyFormComponent />
</AccessThread>
```

### AccessThread

```js
import { AccessThread } from '@kames/3box-system'
const Component = props =>
<AccessThread
  space='web3'
  thread='comments'
  threadOptions={
    members: true,
  }
>
  <MyFormComponent />
</AccessThread>
```

### Threads

#### ThreadJoin

```js
import {ThreadJoin} from '@kames/3box-system';
const Component = props => {
  return (
    <ThreadJoin space="web3" threadName="comments">
      <span>Join Thread</span>
    </ThreadJoin>
  );
};
```

#### PostPublish

```js
import {PostPublish} from '@kames/3box-system';
const Component = props => {
  return (
    <PostPublish threadName="comments">
      <span>delete thread message</span>
    </PostPublish>
  );
};
```

### PostDelete

```js
import {PostDelete} from '@kames/3box-system';
const Component = props => {
  return (
    <PostDelete threadName="comments" postId="123456689">
      <span>Delete Message</span>
    </PostDelete>
  );
};
```
