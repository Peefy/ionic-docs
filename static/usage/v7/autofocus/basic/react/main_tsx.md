```tsx
import React from 'react';
import { IonRouterOutlet } from '@ionic/react';
import { IonReactRouter } from '@ionic/react-router';

import { Route } from 'react-router';

import Example from './pages/Example';

function App() {
  return (
    <IonReactRouter>
      <IonRouterOutlet>
        <Route path="/" render={() => <Example />} />
      </IonRouterOutlet>
    </IonReactRouter>
  );
}
export default App;
```
