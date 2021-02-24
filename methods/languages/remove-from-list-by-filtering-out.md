# Task

Remove an element from a list.

# Solution method

Filter out the element being removed. Override the old list by the filtered out one.

# Example

A user logged in on multiple devices. Each device has its own auhotization token. The user requested logging out from one device. 
The system (API service) should remove the authorization token for that device. A simplified Node JS version of HTTP API:

```javascript
api.post('/users/logout', async (req, res) => {
  // Get current device token from the Authourization header
  const tokenToRemove = req.headers['Authorization'];

  // Retrieve the user and his/her tokens from a storage repository
  const user = repo.users.find({_id :  req.query.id});
  
  // Apply the "Filter out method"
  user.tokens = user.tokens.filter((token) => token != tokenToRemove);
  
  // Save back the changes
  repo.users.save(user);
  
}
```
