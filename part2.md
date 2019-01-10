# Home for the Holidays (Part 2)
For this part of the HW you will be completely building out the rest of the project.  I have written user stores for each route below:


### Routes
You should already have each of the following routes.  Now make each route work - the order you go in doesn't really matter so feel free to jump around based on your interest.  Make sure you are appropriately branching - one branch per feature.  Some routes may have more than one feature.

##### /friends
* As a user, I want to see all of my friends.
* As a user, I want to see an affordance to delete a friend, edit a friend, and add a new friend.
* As a user, when I click on the affordance to delete a friend I want that friend to be removed.
* As a user, when I click the affordance to add a new friend, I should be redirected to `/friends/new`.
* As a user, when I click the affordance to edit a friend I should be redirected to `/friends/:id/edit` (the friendId should go in the route instead of :id).

##### /friends/new
* As a user when I am on the new friend page I should see input fields for all the required information and a save button.
* As a user, if I don't fill in all the form elements, I should not be able to click the save button.
* As a user, once I fill out all the form elements and click the save button, the new friend should be saved to Firebase, I should be redirected to `/friends`, and I should see the friend I just created in my list.

##### /friends/:id/edit
* As a user, when I am on the edit page for a friend, I should see all the form elements from the /new page but populated with the information for the specific friend I am editing.
* As a user, when I update the information in the form elements and click save, the data should flow to Firebase as a PUT request and I should be redirected to `/friends` where I should see the changes I made.


##### /holidays
* As a user, I want to see all of my holidays.
* As a user, I want to see an affordance to delete a holiday, edit a holiday, and add a new holiday.
* As a user, when I click on the affordance to delete a holiday I want that holiday to be removed.
* As a user, when I click the affordance to add a new holiday, I should be redirected to `/holidays/new`.
* As a user, when I click the affordance to edit a holiday I should be redirected to `/holidays/:id/edit` (the holidayId should go in the route instead of :id).


##### /holidays/new
* As a user when I am on the new holidays page I should see input fields for all the required information and a save button.
* As a user, if I don't fill in all the form elements, I should not be able to click the save button.
* As a user, once I fill out all the form elements and click the save button, the new holiday should be saved to Firebase, I should be redirected to `/holidays`, and I should see the holiday I just created in my list.

##### /holidays/:id
* As a user when I am on the detail page for a holiday I should see all the information about the holiday including a guest list.
* As a user, when I click on an affordance to add friends to a holiday, I should be redirected to `/holidays/:id/friends` (the holidayId should go in the route instead of :id).

##### /holidays/:id/edit
* As a user, when I am on the edit page for a holiday, I should see all the form elements from the /new page but populated with the information for the specific holiday I am editing.
* As a user, when I update the information in the form elements and click save, the data should flow to Firebase as a PUT request and I should be redirected to `/holidays` where I should see the changes I made.

##### /holidays/:id/friends
* As a user, when I am on the HolidayFriends page I should be able to see all my friends with check boxes next to them indicating if they are coming or not.
* As a user, when I click on a checkbox next to a friend, Firebase should get updated (FriendHoliday collection - should have friendId, HolidayId, IsComing=true)