// app.js - Complete Firebase Integration for StudyHub

// --------------------
// Firebase Setup
// --------------------
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};

firebase.initializeApp(firebaseConfig);
const auth = firebase.auth();
const db = firebase.firestore();
const storage = firebase.storage();

// --------------------
// Search Functionality
// --------------------
const searchInput = document.querySelector('.search-box input');
if(searchInput){
    searchInput.addEventListener('input', () => {
        console.log('Searching:', searchInput.value);
    });
}

// --------------------
// Card Clicks
// --------------------
const subjectCards = document.querySelectorAll('.card');
subjectCards.forEach(card => {
    card.addEventListener('click', () => {
        alert(Opening ${card.textContent}...);
    });
});

const trendingItems = document.querySelectorAll('.trend-item');
trendingItems.forEach(item => {
    item.addEventListener('click', () => {
        alert(Opening: ${item.textContent});
    });
});

// --------------------
// Sign Up
// --------------------
const signupForm = document.querySelector('#signupForm');
if(signupForm){
    signupForm.addEventListener('submit', (e) => {
        e.preventDefault();
        const name = signupForm.name.value;
        const email = signupForm.email.value;
        const password = signupForm.password.value;

        auth.createUserWithEmailAndPassword(email, password)
            .then(userCredential => {
                return db.collection('users').doc(userCredential.user.uid).set({
                    name: name,
                    email: email,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
            })
            .then(() => {
                alert('Sign Up Successful');
                window.location.href = 'login.html';
            })
            .catch(error => alert(error.message));
    });
}

// --------------------
// Login
// --------------------
const loginForm = document.querySelector('#loginForm');
if(loginForm){
    loginForm.addEventListener('submit', (e) => {
        e.preventDefault();
        const email = loginForm.email.value;
        const password = loginForm.password.value;

        auth.signInWithEmailAndPassword(email, password)
            .then(() => {
                window.location.href = 'dashboard.html';
            })
            .catch(error => alert(error.message));
    });
}

// --------------------
// Auth State Check
// --------------------
auth.onAuthStateChanged(user => {
    if(!user){
        if(window.location.pathname.includes('dashboard.html') || window.location.pathname.includes('admin.html')){
            window.location.href = 'login.html';
        }
    }
});

// --------------------
// Dashboard Dynamic Data
// --------------------
const dashboardBookmarks = document.querySelector('#dashboardBookmarks');
const dashboardPurchases = document.querySelector('#dashboardPurchases');
if(dashboardBookmarks || dashboardPurchases){
    auth.onAuthStateChanged(user => {
        if(user){
            db.collection('bookmarks').where('uid','==',user.uid).get()
            .then(snapshot => {
                if(snapshot.empty){
                    dashboardBookmarks.innerHTML = '<p>No bookmarks yet</p>';
                } else {
                    dashboardBookmarks.innerHTML = '';
                    snapshot.forEach(doc => {
                        const data = doc.data();
                        const div = document.createElement('div');
                        div.className = 'trend-item';
                        div.textContent = data.title;
                        dashboardBookmarks.appendChild(div);
                    });
                }
            });

            db.collection('purchases').where('uid','==',user.uid).get()
            .then(snapshot => {
                if(snapshot.empty){
                    dashboardPurchases.innerHTML = '<p>No purchases yet</p>';
                } else {
                    dashboardPurchases.innerHTML = '';
                    snapshot.forEach(doc => {
                        const data = doc.data();
                        const div = document.createElement('div');
                        div.className = 'trend-item';
                        div.textContent = data.title;
                        dashboardPurchases.appendChild(div);
                    });
                }
            });
        }
    });
}

// --------------------
// Admin Upload Forms
// --------------------
const noteUploadForm = document.querySelector('#noteUploadForm');
if(noteUploadForm){
    noteUploadForm.addEventListener('submit', (e)=>{
        e.preventDefault();
        const file = noteUploadForm.file.files[0];
        const title = noteUploadForm.title.value;
        const cls = noteUploadForm.class.value;
        const subject = noteUploadForm.subject.value;

        const storageRef = storage.ref(notes/${file.name});
        storageRef.put(file).then(()=>{
            storageRef.getDownloadURL().then(url=>{
                db.collection('notes').add({
                    title: title,
                    class: cls,
                    subject: subject,
                    fileUrl: url,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                alert('Note Uploaded');
            });
        });
    });
}

const pyqUploadForm = document.querySelector('#pyqUploadForm');
if(pyqUploadForm){
    pyqUploadForm.addEventListener('submit', (e)=>{
        e.preventDefault();
        const file = pyqUploadForm.file.files[0];
        const title = pyqUploadForm.title.value;
        const cls = pyqUploadForm.class.value;
        const subject = pyqUploadForm.subject.value;
        const year = pyqUploadForm.year.value;

        const storageRef = storage.ref(pyqs/${file.name});
        storageRef.put(file).then(()=>{
            storageRef.getDownloadURL().then(url=>{
                db.collection('pyqs').add({
                    title: title,
                    class: cls,
                    subject: subject,
                    year: year,
                    fileUrl: url,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                alert('PYQ Uploaded');
            });
        });
    });
}

const tutorUploadForm = document.querySelector('#tutorUploadForm');
if(tutorUploadForm){
    tutorUploadForm.addEventListener('submit', (e)=>{
        e.preventDefault();
        const image = tutorUploadForm.image.files[0];
        const name = tutorUploadForm.name.value;
        const subject = tutorUploadForm.subject.value;
        const experience = tutorUploadForm.experience.value;
        const rating = tutorUploadForm.rating.value;

        const storageRef = storage.ref(tutors/${image.name});
        storageRef.put(image).then(()=>{
            storageRef.getDownloadURL().then(url=>{
                db.collection('tutors').add({
                    name: name,
                    subject: subject,
                    experience: experience,
                    rating: rating,
                    imageUrl: url,
                    createdAt: firebase.firestore.FieldValue.serverTimestamp()
                });
                alert('Tutor Uploaded');
            });
        });
    });
}
