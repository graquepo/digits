![](https://raw.githubusercontent.com/graquepo/digits/main/doc/real-landing.JPG?token=GHSAT0AAAAAABYV46NGKQPZ2G22BAXCSNKQY3J6HLA)

## Installation

First, [install Meteor](https://www.meteor.com/install).

Second, go to [https://github.com/graquepo/digits](https://github.com/ics-software-engineering/meteor-application-template-react), and click the "Use this template" button. Complete the dialog box to create a new repository that you own that is initialized with this template's files.

Third, go to your newly created repository, and click the "Clone or download" button to download your new GitHub repo to your local file system.  Using [GitHub Desktop](https://desktop.github.com/) is a great choice if you use MacOS or Windows.

Fourth, cd into the app/ directory of your local copy of the repo, and install third party libraries with:

```
$ meteor npm install
```

## Running the system

Once the libraries are installed, you can run the application by invoking the "start" script in the [package.json file](https://github.com/ics-software-engineering/meteor-application-template-react/blob/master/app/package.json):

```
$ meteor npm run start
```

The first time you run the app, it will create some default users and data. Here is the output:

```
 meteor npm run start 

> meteor-application-template-react@ start /Users/carletonmoore/GitHub/ICS314/meteor-application-template-react/app
> meteor --no-release-check --exclude-archs web.browser.legacy,web.cordova --settings ../config/settings.development.json

[[[[[ ~/GitHub/ICS314/meteor-application-template-react/app ]]]]]

=> Started proxy.                             
=> Started HMR server.                        
=> Started MongoDB.                           
I20221107-19:28:24.602(-10)? Creating the default user(s)
I20221107-19:28:24.612(-10)?   Creating user admin@foo.com.
I20221107-19:28:24.679(-10)?   Creating user john@foo.com.
I20221107-19:28:24.750(-10)? Creating default contacts.
I20221107-19:28:24.751(-10)?   Adding: Johnson (john@foo.com)
I20221107-19:28:24.775(-10)?   Adding: Casanova (john@foo.com)
I20221107-19:28:24.778(-10)?   Adding: Binsted (admin@foo.com)
I20221107-19:28:24.833(-10)? Monti APM: completed instrumenting the app
=> Started your app.

=> App running at: http://localhost:3000/
```

Periodically, you might see `Error starting Mongo (2 tries left): Cannot run replSetReconfig because the node is currently updating its configuration` after the `=> Started HMR server.`. It doesn't seem to be a problem since the MongoDB does start.

### Viewing the running app

If all goes well, the template application will appear at [http://localhost:3000](http://localhost:3000).  You can login using the credentials in [settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json), or else register a new account.

### ESLint

You can verify that the code obeys our coding standards by running ESLint over the code in the imports/ directory with:

```
meteor npm run lint
```

## Walkthrough

The following sections describe the major features of this template.

#### Landing page

When you retrieve the app at http://localhost:3000, this is what should be displayed:

![](https://raw.githubusercontent.com/graquepo/digits/main/app/public/images/real-landing.JPG?token=GHSAT0AAAAAABYV46NGUYYT3KNVQIWNQHHIY3J5OJQ)

The next step is to use the Login menu to either Login to an existing account or register a new account.

#### Login page

Clicking on the Login link, then on the Sign In menu item displays this page:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/login-page.JPG?token=GHSAT0AAAAAABYV46NH6GZWHEMW2ASOKKXKY3J6QWA)

#### Register page

Alternatively, clicking on the Login link, then on the Sign Up menu item displays this page:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/register-page.JPG?token=GHSAT0AAAAAABYV46NHQTV6IPPTLTUZGPMGY3J6HZQ)


#### Landing (after Login) page, non-Admin user

Once you log in (either to an existing account or by creating a new one), the navbar changes as follows:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/landing-page-john.JPG?token=GHSAT0AAAAAABYV46NHLWTUYXI7VSEYO66AY3J6M2Q)

You can now add new Contacts documents, and list the Contacts you have created. Note you cannot see any Contacts created by other users.

#### Add Contacts page

After logging in, here is the page that allows you to add new Contacts:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/add-contact.JPG?token=GHSAT0AAAAAABYV46NHGT63GQ3NN6BLPSUMY3J6IIQ)

#### List Contacts page

After logging in, here is the page that allows you to list all the Contacts you have created:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/list-contacts.JPG?token=GHSAT0AAAAAABYV46NH4KHSEKGE6AEVY3UWY3J6QMA)

You click the "Edit" link to go to the Edit Contacts page, shown next.

#### Edit Contacts page

After clicking on the "Edit" link associated with an item, this page displays that allows you to change and save it:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/edit-contacts.JPG?token=GHSAT0AAAAAABYV46NHCUFGXPZP3PLOT762Y3J6MAA)

#### Landing (after Login), Admin user

You can define an "admin" user in the settings.json file. This user, after logging in, gets a special entry in the navbar:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/landing-page.JPG?token=GHSAT0AAAAAABYV46NHL4J47VMQGVEA7HRSY3J6QAA)

#### Admin page (list all users contacts)

To provide a simple example of a "super power" for Admin users, the Admin page lists all of the Stuff by all of the users:

![](https://raw.githubusercontent.com/graquepo/digits/main/doc/admin-page.JPG?token=GHSAT0AAAAAABYV46NHLUDZMVKIDQJ7CQTIY3J6I6Q)

Note that non-admin users cannot get to this page, even if they type in the URL by hand.

### CSS

The application uses the [React implementation of Bootstrap 5](https://react-bootstrap.github.io/). You can adjust the theme by editing the `app/client/style.css` file. To change the theme override the Bootstrap 5 CSS variables.

```css
/* Use Open Sans as the default sans serif font. */
@import url("https://fonts.googleapis.com/css?family=Open+Sans:300,400,500,700|Source+Code+Pro:300,400,500,700");

/* Set up some CSS variables to theme the application. */
:root {
  --matr-navbar-bg: deeppink;
  --matr-navbar-bg-rgb: 255, 182, 193;
  --matr-navbar-text-color: white;
  --matr-navbar-highlight-text: deeppink;
}

/* Change bootstrap variable values.
 See https://getbootstrap.com/docs/5.2/customize/css-variables/
 */
body {
  --bs-dark: var(--matr-navbar-bg);
  --bs-dark-rgb: var(--matr-navbar-bg-rgb);
  background-size: cover;
  background: fixed center url("images/clouds.png");
}

body .navbar {
  --bs-navbar-active-color: var(--matr-navbar-highlight-text);
  --bs-navbar-brand-color: var(--matr-navbar-text-color);
  --bs-navbar-brand-hover-color: var(--matr-navbar-highlight-text);
  --bs-navbar-color: var(--matr-navbar-text-color);
  --bs-navbar-hover-color: var(--matr-navbar-highlight-text);
}

.bg-dark a.dropdown-item {
  color: var(--matr-navbar-bg);
}

/* Set the alert background on the signin and signup pages. */
#signin-page .alert-light, #signup-page .alert-light {
  --bs-alert-bg: var(--matr-navbar-bg);
}

/* Define custom styles */
.gray-background {
  background-color: var(--matr-navbar-bg);
  color: var(--bs-dark);
  padding-top: 10px;
  padding-bottom: 20px;
}

footer, footer a {
  color: var(--matr-navbar-text-color);
}

.navbar a.nav-link.active {
  color: var(--matr-navbar-highlight-text);
}
```

### Routing

For display and navigation, the application uses [React Router](https://reacttraining.com/react-router/).

Routing is defined in [imports/ui/layouts/App.jsx](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/app/imports/ui/layouts/App.jsx).


### Authentication

For authentication, the application uses the Meteor accounts package.

When the application is run for the first time, a settings file (such as [config/settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json)) should be passed to Meteor. That will lead to a default account being created through the code in [imports/startup/server/accounts.js](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/app/imports/startup/server/accounts.js).

The application allows users to register and create new accounts at any time.

### Authorization

Only logged in users can manipulate Contacts documents (but any registered user can manipulate any Contacts document, even if they weren't the user that created it.)

### Configuration

The [config](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config) directory is intended to hold settings files.  The repository contains one file: [config/settings.development.json](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/config/settings.development.json).

The [.gitignore](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/.gitignore) file prevents a file named settings.production.json from being committed to the repository. So, if you are deploying the application, you can put settings in a file named settings.production.json and it will not be committed.

### Quality Assurance

#### ESLint

The application includes a [.eslintrc](https://github.com/ics-software-engineering/meteor-application-template-react/blob/main/app/.eslintrc) file to define the coding style adhered to in this application. You can invoke ESLint from the command line as follows:

```
[~/meteor-application-template-react/app]-> meteor npm run lint

> meteor-application-template-react@ lint /Users/philipjohnson/meteor-application-template-react/app
> eslint --quiet ./imports
```

ESLint should run without generating any errors.

It's significantly easier to do development with ESLint integrated directly into your IDE (such as IntelliJ).
