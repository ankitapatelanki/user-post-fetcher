
 // API Endpoint: https://jsonplaceholder.typicode.com/posts




   async function getAllUsersData(){
            let response = await fetch("https://jsonplaceholder.typicode.com/posts")
            let data = await response.json()
            return data;
        }
        // let responseData = await getAllUsersData()
        // console.log(responseData)

// Question 1: Fetch all posts by a specific user based on userId.
        async function getAllPostByUserId(userIdnum){
          let dataForAllPost=await getAllUsersData()
          let allPostData=[]
          for(let i=0; i<dataForAllPost.length-1; i++){
            if(dataForAllPost[i].userId==userIdnum){
               allPostData.push(dataForAllPost[i]) 
            }
          }
          return allPostData
        }
        let resultForAllPost  = await getAllPostByUserId(1)
        // console.log(resultForAllPost)


// Question 2: Fetch a single post based on its id.
           async function fetchSingleData(id){
                let allRecord=await getAllUsersData()
                for(let i=0; i<=allRecord.length-1; i++){
                    if(allRecord[i].id==id){
                        return allRecord[i]
                    }
                }
            }
            // let singlePostDataById= await fetchSingleData(2)
            // console.log(singlePostDataById)


// Question 3: Fetch only 3 posts for a given userId.
                async function fetch3PostByUserId(userId) {
                    let allRecord=await getAllUsersData()
                    for(let i=0; i<=allRecord.length-1; i++){
                        if(allRecord[i].userId===userId){
                            return allRecord[i].userId.length;
                            }
                        
                    }
                }
                let getOnly3Records = await fetch3PostByUserId(1)
                console.log(getOnly3Records)



// Question 4: Fetch a post by its id and return only the title and userId.
                async function  getReturnTitleAndUserId(id) {
                 let allRecord=await getAllUsersData()
                 for(let i=0; i<=allRecord.length-1; i++){
                        if(allRecord[i].id==id){
                            return 'title:'+ allRecord[i].title + '  ' +'userId:' + allRecord[i].userId
                        }
                        }
                        }
                    // let getTitleAndUserId= await getReturnTitleAndUserId(2)
                    // console.log(getTitleAndUserId)




// Question 5: Fetch a post by its id, update the body content to: 
// -> "Hello, This is updated content..." and return the complete updated object.

// Question 6: Return all posts where the id is an even number.
                        async function rerturnAllEvenNumPost(idNum) {
                            let allRecord=await getAllUsersData()
                            let evenIds=[]                           
                         for(let i=0; i<=allRecord.length-1; i++){
                            if(allRecord[i].id%2==0){
                                evenIds.push(allRecord[i])
                            }
                        }return evenIds;
                    }
                        // let getAllEvenId =await rerturnAllEvenNumPost(2)
                        // console.log(getAllEvenId)


// Question 7: Return all posts where the id is an odd number.
                    async function rerturnAllOddNumPost(OddIdNum) {
                          let allRecord=await getAllUsersData()
                          let oddIds=[]
                          for(let i=0; i<=allRecord.length-1; i++){
                            if(allRecord[i].id%2!==0){
                                oddIds.push(allRecord[i])
                            }
                          }return oddIds;
                    }
                    // let getOddId = await rerturnAllOddNumPost(1)
                    // console.log(getOddId)


// Question 8: Take an id as a parameter, find the corresponding post, and return the sum of userId and id.
                    async function getSumOfuserIdAndID(enterId) {
                          let allRecord=await getAllUsersData()
                          let sumids=[]
                          for(let i=0; i<=allRecord.length-1; i++){
                            if(allRecord[i].id==enterId){
                                sumids.push(allRecord[i].userId +allRecord[i].id)  
                            }
                          }return sumids
                    }
                    // let returnSumOfIds= await getSumOfuserIdAndID(97)
                    // console.log(returnSumOfIds)


// Question 9: Take an id as a parameter, find the corresponding post, append "-example new string added" to the end of the title, and return the updated object.
                    async function returnUpdatedObjbyId(IDNumber) {
                        let allRecord=await getAllUsersData()
                        // let editTitle={}
                        for(let i=0; i<=allRecord.length-1; i++){
                            if(allRecord[i].id==IDNumber){
                                let editTitle={}
                                let userId = allRecord[i].userId;
                                let id = allRecord[i].id;
                                let title = allRecord[i].title + "-example new string added";
                                let body = allRecord[i].body;
                                editTitle={'userId':userId ,'id':id, 'title':title,'body':body}

                                // return allRecord[i].userId+allRecord[i].id +allRecord[i].title + "-example new string added" +allRecord[i].body
                                return editTitle;
                            }
                        }
                    }
                    // let updatedTitle= await returnUpdatedObjbyId(99)
                    // console.log(updatedTitle)


// Question 10: Take an id as a parameter, find the corresponding post, and add the following new key to the object:
// comments: { userRate: 10, userName: "xyz", ph: 8448484848 }
// Return the updated object.
                    async function addNewKeyInObj(byId) {
                        let allRecord=await getAllUsersData()
                        let addKey ={userRate: 10, userName: "xyz", ph: 8448484848}
                        for(let i=0; i<=allRecord.length-1; i++){
                            if(allRecord[i].id==byId){ 
                                allRecord[i].addKey ={
                                    userRate: 10, 
                                    userName: "xyz", 
                                    ph: 8448484848
                                }
                                //   addKey.push(allRecord[i])
                            //  let addKey =allRecord[i].addKey+ {userRate: 10, userName: "xyz", ph: 8448484848};
                            //  addKey ={addKey:allRecord[i]+{userRate: 10, userName: "xyz", ph: 8448484848}}                  
                                return allRecord[i]
                                // return addKey
                            }}
                        
                    }
                    let addedNewKeys = await addNewKeyInObj(99)
                    console.log(addedNewKeys)# user-post-fetcher
