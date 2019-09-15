# haunted-robot

[Haunted](https://github.com/matthewp/haunted) hooks for use with [Robot](https://thisrobot.life/).

## Installation

Via npm:

```shell
npm install haunted-robot --save
```

Or Yarn:

```shell
yarn add haunted-robot
```

## Usage

```js
import { useMachine } from 'haunted-robot';
import { html, component } from 'haunted';

const machine = createMachine({
  one: state(
    transition('next', 'two')
  ),
  two: state()
});

function App() {
  const [current, send] = useMachine(machine);
  
  return html`
    <button type="button" @click=${() => send('next')}>
      State: ${current.name}
    </button>
  `;
}

customElements.define('my-app', component(App));
```

## License

BSD-2-Clause