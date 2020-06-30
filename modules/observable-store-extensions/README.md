## Observable Store Extensions

[Observable Store](https://github.com/DanWahlin/Observable-Store) is a front-end state management library that provides a simple yet powerful way to manage state in front-end applications. 

This package can be used to integrate Observable Store with the [Redux DevTools](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd). View more details about using the extensions [here](https://github.com/DanWahlin/Observable-Store#extensions).

### Changes

#### 2.2.6 - January 25, 2020

Change how detection for presence of redux devtools is done. Don't send state back to devtools while using time travel or jumping to a specific action (debugging scenarios).

#### 2.2.7 - May 11, 2020

Added workaround for changed APIs for accessing providers/services in Angular 9+. User must now pass the Router and ngZone symbols when
enabling the Redux Devtools. See project repository repo for more details.

```typescript
import { environment } from './environments/environment';
import { NgZone } from '@angular/core';
import { Router } from '@angular/router';

if (!environment.production) {
    ObservableStore.addExtension(new ReduxDevToolsExtension());
}
```

#### 2.2.8 - May 20, 2020

Added support for Angular Ivy with the Redux DevTools. Breaking changes in Ivy prevented this functionality initially, but thanks to help from
<a href="https://https://github.com/atscott" target="_blank">Andrew Scott</a> and <a href="https://https://https://github.com/Coly010" target="_blank">Colum Ferry</a> it's now working with the following code:

```typescript
import { environment } from './environments/environment';
import { NgZone } from '@angular/core';
import { Router } from '@angular/router';

if (!environment.production) {
    ObservableStore.addExtension(new ReduxDevToolsExtension({ router: Router, ngZone: NgZone }));
}
```