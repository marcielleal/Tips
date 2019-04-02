# LaravelTips
This is a repository to store tips and tricks of Laravel 5.

Author: [Marciel Leal](https://github.com/marcielleal)

Email: marcielmanoel15@gmail.com

## Database
### Foreign keys on Laravel's migrations
You **need** to declare the foreign key as an unsigned integer. Nobody seems to know why exactly.

## Views
### Scripts
Apparently, all scripts outside of sections are not executed.

## Routes
### route vs url
Both generates a full url from a string. **url** needs a parameter which is a local url from the project. route needs a parameter which is the name of the route.
