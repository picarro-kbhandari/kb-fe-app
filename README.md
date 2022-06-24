


## Project Structure 
1. Components 
    All components that are created will be placed inside this directiory. 
2. utils 
    Utils will contains all resuable modules and helper functions.
3. apis
    Apis will contain logic to interact with the backend.
4. configs 
    Configs do all the nessessory configs for the application to run.



# Example - Create React App

This exampel for the registration and user pages for how to screen the video.


if (user.isActive === '') {
  const newUser = {
    id: user.id,
    username: user.username,
    genres: user.genres,
    isActive: 'button-is-active'
  }
  const newData = [...usersData]
  newData.splice(index, 1, newUser)

  const update = () => updateUsersData(newData)
  update()

  const newFollow = { following: [{ id: user.id }, ...currentUser] }

  axios.put('/api/follow', newFollow, {
    headers: { Authorization: `Bearer ${token}` }
    })
    .then(resp => {
      updateUser(resp.data.following)
    })
} 

# Exmple
Updatig the users interests on the Create and edit user page.
When the genre button is clicked it checks the value sets the id for a function and updates the state of the button. 
Then it calls a function to check if the genre selected exists in the genre form data - and adds or removes depending on the result. The form data object is then updated with the new genre array -

  let id = null
  const array = formData.genres
 
    // An Entry for each Genre
  if (e.target.value === 'Lifestyle') {
    id = 12
    if (lifeClass === '') {
      lifeUpdate('genre-button-active')
    } else {
      lifeUpdate('')
    }
  }
    // ...
  addOrRemove(array, id)

  function addOrRemove(array, id) {
    const obj = { id: id }
    var index = array.findIndex(x => x.id === id)
    if (index === -1) {
      array.push( obj )
    } else {
      array.splice(index, 1)
    }

    const data = {
      ...formData,
      genres: array
    }

    updateFormData(data)

  }







----------------------

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

