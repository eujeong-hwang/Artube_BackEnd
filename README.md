# ARTUBE
Use ARTUBE and share art-related youtube videos! 

## 1. Project Duration & Team Members

- October 11, 2021 ~ October 16, 2021
- 6 Team Members
   - Backend (Node.js)
    Suneung Park, Sung gyu An, Eu Jeong Hwang
    
   - Frontend (React)
    Dawon Kim, Duk hyun Kim, Hyo Jin Kim

## 2. Technologies Used

- `Backend`
   - Node.js
   - Express
- `DB`
   - MongoDB


## 3. API Design & WireFrame
https://www.notion.so/dawon-ella-kim/1-Artube-bee37ad5fbbe4663a24056ea7f85580a


## 4. Video of ARTUBE
[![Video Label](http://img.youtube.com/vi/qYR1lIZq4CY/0.jpg)](https://www.youtube.com/watch?v=qYR1lIZq4CY)
- https://www.youtube.com/watch?v=qYR1lIZq4CY



## 5. Main Functions

- LogIn, SignUp
   - Used Json Web Token for verification
   - ID should contain more than 3 words, numbers, english in lower/upper case
   - Password should contain more than 4 words, numbers, english in lower/upper case
   - Password should not contain the strings that is in the ID

- User Profile
   - Read, Update, Delete user profile

- Post Artube vidoes CRUD
   - User can post art-related youtube videos
   - User can view other user's post
   - After user authorization, user can update & delete their post
   
- Comment CRUD
   - User can write a comment on Artube posts.
   - User can view other user's comments
   - After user authorization, user can update & delete their comment 
   
## 6. What we have solved
`backend`
 - When we want to delete an information from the user profile, how can we delete only the specific db key and value, not the whole db values? 
    - If we use User.deleteOne(), _id, userId, password, userPic, userIntro, the key of User db, is deleted entirely. 
    - So to only delete userPic, userIntro from the db, we used findOneAndUpdate(), and gave the userPic and userIntro a null value.
        
        ```jsx
        await User.findOneAndUpdate(
                    { userId: user.userId },
                    { $set: { userIntro : null, userPic : null }}
        )
        ```
        
