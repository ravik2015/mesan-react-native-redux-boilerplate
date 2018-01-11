# React Native Redux Boilerplate

Boilerplate for a React Native iOS and Android app using Redux

<a name="step1"></a>
### Step 1: Create React Native Project

Open terminal and run
```bash
react-native init ProjectName
```

<a name="step2"></a>
### Step 2: Install Dependencies

In your project root, run
```bash
npm install --save react-redux
npm install --save redux
npm install --save redux-thunk
```

<a name="step3"></a>
### Step 3: Create Folder Structure

In your project root create an <b>app</b> folder. In the app folder create an <b>actions</b> folder , a <b>reducers</b> folder and a <b>components</b> folder.


<a name="step4"></a>
### Step 4: Create Your First Action

The action is a basic function called from the component whenever we want the whole state of the app to be changed.
Our action creator is a simple function returning an object (the action itself)with a type attribute expressing what happened with the app.
<br>
In your actions folder create a js file <b>index.js</b>

```javascript
export const DATA_AVAILABLE = 'DATA_AVAILABLE';

import Data from '../../instructions.json';

export function getData(){
    return (dispatch) => {

        //Make API Call
        //For this example, I will be retrieving data from a json file
        //Get the sample data in the json file
        //delay the retrieval [Sample reasons only]
        setTimeout(() => {
            var data  = Data.instructions;
            dispatch({type: DATA_AVAILABLE, data:data});
        }, 2000);

    };
}

```

<a name="step5"></a>
### Step 5: Create Your First Reducer

Reducers are the ones in charge of updating the state of the app. Redux will automatically pass the current state of the app and the action occurred.
It’s up to the reducer to realize if it needs to modify the state or not based on the action.type.
<br>

<a name="step6"></a>
### Step 6: Create Your Component

In your components folder create a js file <b>home.js</b>


<a name="step7"></a>
### Step 7: Create Your Store

In the app folder, create a js file <b>store.js</b>


<a name="step8"></a>
### Step 8: Link It All Together

Redux needs to inject a store holding the app state into the app.
To do so, it requires a ‘Provider’ wrapping the whole app.
