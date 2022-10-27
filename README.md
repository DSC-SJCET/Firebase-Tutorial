# Firebase-Tutorial
Firebase tutorial

step 1 : Clone the code 

step 2 : setup firebse and paste the configuration code (configration code example given below ##Don't COPY THIS CONFIGRATION CODE IT'S UNIQUE FOR ALL) on html file            below body tag ( </body> )

    <script type="module">
    // Import the functions you need from the SDKs you need
    import { initializeApp } from "https://www.gstatic.com/firebasejs/9.12.1/firebase-app.js";
    // TODO: Add SDKs for Firebase products that you want to use
    // https://firebase.google.com/docs/web/setup#available-libraries

    // Your web app's Firebase configuration
    const firebaseConfig = {
        apiKey: "AIzaSyC_Acy3h5J5Egbj8Mc1CxAXCaS3M-hEWDs",
        authDomain: "fir-4b6c7.firebaseapp.com",
        projectId: "fir-4b6c7",
        storageBucket: "fir-4b6c7.appspot.com",
        messagingSenderId: "643012676626",
        appId: "1:643012676626:web:6cf897e4f8fc5df55e9ccb"
    };

    // Initialize Firebase
    const app = initializeApp(firebaseConfig);
    </script>
    
    
    
step 3 : paste the below code in the script (consider the figure 1:import packages)

    import { getFirestore, addDoc, collection, getDocs } from 'https://www.gstatic.com/firebasejs/9.12.1/firebase-firestore.js'
    
![image](https://user-images.githubusercontent.com/70875875/198297933-c2294803-3b28-4567-bfba-483602ee3a15.png)

step 4 : Paste the below code for initialize database (note highlighted area Figure 3:Database initilizing)

     const db = getFirestore(app);
     
![image](https://user-images.githubusercontent.com/70875875/198299526-b6e3adaf-41ab-44c6-9cfa-212669a0557b.png)
     
step 5 : Paste the below code to data sent (like in figure 2:data sending)

## Data send

    document.getElementById("submit-btn").onclick = async function (e) {
        e.preventDefault()
        const docRef = await addDoc(collection(db, "data"), {
            Name: document.getElementById('Name').value,
            Message: document.getElementById('Msg').value
        });
        console.log("Document written with ID: ", docRef.id);
        alert("Form submitted")
    };
    
![image](https://user-images.githubusercontent.com/70875875/198313338-7e9f81eb-8948-4254-a3de-0f6c8fe90fad.png)

step 5 : Paste the below code as in picture (note Figure 3:Data sending)

## Data Calling

    window.onload = async function () {
        const querySnapshot = await getDocs(collection(db, "data"));
        querySnapshot.forEach((doc) => {
            const row = document.getElementById("tbody").insertRow(0);
            row.insertCell(0).innerHTML = doc.data().Name
            row.insertCell(-1).innerHTML = doc.data().Message
        });
    }

![image](https://user-images.githubusercontent.com/70875875/198315253-60427304-4025-47ba-a3e7-f40742b0f44f.png)

step 6 : Type somthing in website form and submit. Then refresh the website to see the change (note in video)


[![Alternate Text]({https://firebase.google.com/images/social.png})]({https://drive.google.com/file/d/1vwiu2DTNKKI4yPL1jHmqnzp9lobN49M1/view?usp=sharing} "Link Title")
