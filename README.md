# NgVdom

Major rewrite in progress.
Logic organization inspired by [Inferno](https://github.com/infernojs/inferno/).

## Usage

Global bootstrap without Angular API:

```tsx
// Any react-compatible jsxFactory would be fine
import * as React from 'react'
import { render } from 'ng-vdom/bootstrap'

render(
  <h1>Hello World</h1>,
  document.querySelector('root')
)
```

Render Virtual DOM inside Angular:

```tsx
import { Component, NgModule } from '@angular/core'
import { VDomModule } from 'ng-vdom'

@Component({
  template: `
    <v-outlet [element]="element"></v-outlet>
  `
})
export class AppComponent {
  element = <h1>Hello World</h1>
}

@NgModule({
  declarations: [ AppComponent ],
  imports: [ VDomModule ],
})
export class AppModule { }
```

[Online Demo](https://stackblitz.com/edit/angular-vjj9vt?file=src%2Fapp%2Fclock.ts).
