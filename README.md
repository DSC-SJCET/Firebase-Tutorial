# Firebase-Tutorial
Firebase tutorial

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
