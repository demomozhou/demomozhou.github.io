# React LMS

* This project was bootstrapped with Create React App.
* Developed by Jiangren Full Stack Summer 2017-18 Team A

## LMS Frontend Demo

* [https://demomozhou.github.io/#/](https://demomozhou.github.io/#/)

## LMS Backend API

* [https://lms-service.azurewebsites.net/swagger/](https://lms-service.azurewebsites.net/swagger/)
* Swagger UI view

### LMS Backend API Directory

    LMS_Summer_Team_A
    ├── LMS_Summer_Team_A.csproj
    ├── Program.cs
    ├── Startup.cs
    ├── Migrations
    ├── Properties
    ├── Model
    │   └── Account.cs
    │   └── Course.cs
    │   └── Enrolment.cs
    │   └── ILMSDataStore.cs
    │   └── LMSDBContext.cs
    │   └── LMSDataStore.cs
    │   └── Lecturer.cs
    │   └── Student.cs
    │   └── StudentAddress.cs
    │   └── Teaching.cs
    └── Controllers
        └── AccountController.cs
        └── CourseController.cs
        └── EnrolmenttController.cs
        └── LecturerController.cs
        └── StudentController.cs
        └── TeachingController.cs

### LMS Frontend Directory

    LMS_Summer_React_A
    ├── README.md
    ├── node_modules
    ├── package.json
    ├── .gitignore
    ├── public
    │   └── favicon.ico
    │   └── index.html
    │   └── manifest.json
    └── src
        └── App.js
        └── index.js
        └── styles.js
        └── Account
        │   └── Login.js
        │   └── Register.js
        └── Api
        │   └── CourseApi.js
        │   └── EnrolmentApi.js
        │   └── LecturerApi.js
        │   └──StudentApi.js
        │   └── TeachingApi.js
        └── App
        │   └── Footer.js
        │   └── Home.js
        │   └── Router.js
        │   └── TopNav.js
        │   └── logo.svg
        └── Course
        │   └── CourseCard.js
        │   └── CourseDetailView.js
        │   └── CoursesView.js
        └── Lecturer
        │   └── LecturerCard.js
        │   └── LecturerDetailView.js
        │   └── LecturersView.js
        └── Student
        │   └── StudentCard.js
        │   └── StudentDetailView.js
        │   └── StudentsView.js
        └── UI
        │   └── AddCourse.js
        │   └── Auth.js
        │   └── CourseList.js
        │   └── DropCourse.js
        │   └── LecturerList.js
        │   └── Loading.js
        │   └── StudentList.js
        └── styles
            └── base.css
            └── bootstrap.min.css
            └── card-view.css
            └── footer.css
            └── loading.css

#### package.json

        "dependencies": {
            "axios": "^0.18.0",
            "react": "^16.2.0",
            "react-confirm-alert": "^1.0.8",
            "react-dom": "^16.2.0",
            "react-gravatar": "^2.6.3",
            "react-icons": "^2.2.7",
            "react-router-dom": "^4.2.2",
            "react-scripts": "^1.1.1",
            "reactstrap": "^5.0.0-beta.2"
        },

##### axios

Use for Promise API

##### react-confirm-alert

react component confirm dialog

##### react-gravatar

React component for rendering a gravatar profile image

##### react-icons

SVG icon, ES6 import icons not icon-font

##### reactstrap

React Components for Bootstrap 4

#### Routes.js

    export default () => ((
        <div>
            <Route exact path="/" component={Home} />
            <Route exact path="/courses" component={CoursesView} />
            <ProtectedRoute exact path="/courses/:id" component={CourseDetailView} />
            <Route exact path="/lecturers" component={LecturersView} />
            <ProtectedRoute exact path="/lecturers/:id" component={LecturerDetailView} />
            <Route exact path="/students" component={StudentsView} />
            <ProtectedRoute exact path="/students/:id" component={StudentDetailView} />
            <Route exact path="/login" component={Login} />
            <Route exact path="/register" component={Register} />
        </div>
    ));

    const ProtectedRoute = ({ component: ProtectedComponent, ...rest }) =>
        <Route
            {...rest} render={props => (
                LoggedIn() ?
                    <ProtectedComponent {...props} />
                    :
                    <Redirect to={{
                        pathname: '/login', state: { from: props.location }
                    }} />
            )}
        />

* React LMS is a one-page web app, not open to public(SEO)
* Use HashRouter instead of BrowserRouter(refresh page will not give 404 error)

### Demo steps

1. Page view(Home, CoursesView, StudentsView, LecturerView, Login, Register)
2. Filter search by name function for Courses, Students, Lecturers(case-insensitive)
3. DetailView pages must loged in, show how to register, login, logout(auth)
4. CRUD for Course, Student, Lecturer(form, input type, required, delete modal)
5. Enrolment and Teaching(add, drop, list view)
6. Others(issues)

## README.md
