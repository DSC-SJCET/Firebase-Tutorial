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
            first_name: document.getElementById('Name').value,
            last_name: document.getElementById('Msg').value
        });
        console.log("Document written with ID: ", docRef.id);
        alert("Form submitted")
    };

![image](https://user-images.githubusercontent.com/70875875/198299971-23a3cf43-473d-40da-8870-2d8d5bf71f3b.png)

step 5 : Paste the below code as in picture (note Figure 3:Data sending)

## Data Calling
    document.getElementById("table").onload = () => { dataCall() }
    async function dataCall() {

    const querySnapshot = await getDocs(collection(db, "data"));
    querySnapshot.forEach((doc,i) => {

        document.getElementById("tbody").insertRow(i).insertCell(i).innerHTML = doc.data().first_name
        document.getElementById("tbody").insertRow(i).insertCell(i++).innerHTML = doc.data().last_name

    });
}

![image](https://user-images.githubusercontent.com/70875875/198301724-a9f7403b-b23f-4e75-90f4-95093348f7cb.png)


step 6 : Type somthing in website form and submit.then goto /table.html to see data (note in video)

