
#  React webV9 firebase CRUD oprations


## config.jsx

### config 

**Note: declare a New jsx file and config firebase firebaseConfig  !**

```
import {initializeApp } from "firebase/app";
import { getFirestore } from 'firebase/firestore/lite';

const firebaseConfig = {
  apiKey: "",
  authDomain: "",
  projectId: "",
  storageBucket: "",
  messagingSenderId: "",
  appId: "",
  measurementId: ""
};

const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);

```


### App.js

#### get values

```
import {  collection, getDocs} from 'firebase/firestore/lite';

import { db } from "./firebase/Config";


 const citiesCol = collection(db, 'products');

 const citySnapshot = await getDocs(citiesCol);


   citySnapshot.docs.forEach(doc => {
          console.log(doc.data(),doc.id);
        })

```


####  add value


```
import {  collection,doc ,addDoc} from 'firebase/firestore/lite';

import { db } from "./firebase/Config";

const citiesCol = collection(db, 'products');

        const docRef = await addDoc(citiesCol, {
          name: "Los Asdxacsagferhbfsdngeles",
          age: 3343240,
          place: "USA"
        });

```

#### delete value 


#### 1.method
```
import {  collection ,deleteDoc} from 'firebase/firestore/lite';


       await deleteDoc(doc(db, "products", "LA")).then(()=>{
          console.log('done');
        })
```

#### 2.method
```
const citiesCol = collection(db, 'products');

        await deleteDoc(doc(citiesCol, "T80tuJeqGdQHrZuXUXKs")).then(()=>{
          console.log('done');
        })

```

#### update value




```
import {  collection ,setDoc,doc} from 'firebase/firestore/lite';

import { db } from "./firebase/Config";


        await setDoc(doc(db, "products",'id'), {
          name: "Los Angeles",
          age: 30,
          place: "USA"
        });
```