# Firebase-Tutorial
Firebase tutorial

First import code in start 

import { getFirestore, addDoc, collection, getDocs } from 'https://www.gstatic.com/firebasejs/9.12.1/firebase-firestore.js'


## Data sent

    const db = getFirestore(app);
    document.getElementById("submit-btn").onclick = async function (e) {
        
            e.preventDefault()
            const docRef = await addDoc(collection(db, "users"), {
                first_name: document.getElementById('Name').value,
                last_name: document.getElementById('Msg').value
            });
            console.log("Document written with ID: ", docRef.id);
            alert("Form submitted")
    };



## Data Calling
    document.getElementById("table").onload = () => { dataCall() }
    async function dataCall() {

    const querySnapshot = await getDocs(collection(db, "users"));
    querySnapshot.forEach((doc,i) => {

        document.getElementById("tbody").insertRow(i).insertCell(i).innerHTML = doc.data().first_name
        document.getElementById("tbody").insertRow( i).insertCell(i++).innerHTML = doc.data().last_name

    });
}
