# Home for the Holidays (Part 1)

### Setup
* Use create-react-app to make a new project called react-holidays
* Do the usual setup we always do
* Create a branch called routes

### Requirements
1. Create A navbar - this should be blank if logged out.  If logged in it should have links for New Friend, Friends, New Holiday, Holidays, and logout.  All links should work.

2.  Create a Public Route - /auth.  It should load a signin with google button when the user is logged out.

3.  Get google authentication working.

4.  Create each of the following PrivateRoutes:

| Route   | Component Name  |  What it should do |
|----------|:-------------:|------:|
| /friends |  Friends | button that goes to /friends/12345/edit  |
| /friends/new |  NewFriend | `<h3>New Friend Page</h3>`  |
| /friends/:id/edit |  EditFriend | `<h3>Edit Friend Page</h3>`  |
| /holidays |  Holidays | button that goes to /holidays/12345  |
| /holidays/new |  NewHoliday | `<h3>New Holiday Page</h3>`  |
| /holidays/:id |  HolidayDetail | button that goes to /holidays/12345/edit and button that goes to /holidays/12345/friends  |
| /holidays/:id/edit |  EditHoliday | `<h3>Edit Holiday Page</h3>`  |
| /holidays/:id/friends |  EditHoliday | `<h3>Add Friends to Holiday Page</h3>`  |

### Tips
Many of the routes above have :id in them.  This is setting a wildcard.  It means when the user clicks on something that takes them to the route the button will provide the id we want to navigate to.  In 95% of our cases :id will become the firebase id.  So the holidays detail page will really look something like: `/holidays/-LVCMi7lTXoKz6Ddzxal`.

In your App.js the detail route should look like this:
```
  <PrivateRoute
    path="/holidays/:id"
    authed={this.state.authed}
    component={HolidayDetail}
  />
```

Once you are on the detail page you generally will need to make a call to firebase to get information back for that holiday.  In order to do that we would generally pass something into props so it is available in the route.  In this case we don't need to pass something into props because we did that when we made the url.  To access the id we can do this:
```
const firebaseId = this.props.match.params.id;
```