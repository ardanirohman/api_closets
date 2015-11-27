# Group Feed
Api Design For Follower Following Feed Discover Recommendation
## Get Followers And Followees [/following/follow{?limit}{?uid}{?page}{?type}]

### List Follow [GET]
+ Parameters

    + limit : 10  (number)
    + uid : 1 (number)
    + page : 1 (number)
    + type : followees (string) - followees or followers
    
+ Response 200 (application/json)

        {
            "type" : "followees",
            "data" :
            [
               {
                    "seller":{
                        "uid":2,
                        "nickname" : "test 2",
                        "avatar" : "test2.jpg",
                        "items_count":10,
                        "followed":true
                    },
                    "product" : [
                        {
                            "id":0,
                            "image":"test.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":1,
                            "image":"test1.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":2,
                            "image":"test1.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":3,
                            "image":"test1.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":4,
                            "image":"test1.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        }
                    ]
                }
            ],
            "limit" : 20,
            "page" : 1
        }

## Follow Unfollow Action [/following/follow]
### Follow Unfollow Action [POST]

+ Request (application/json)

        {
            "followee_uid":20,
            "uid": 2,
            "action" : "follow/unfollow"
        }

+ Response 200 (application/json)

        {
            "status" : true,
            "message" : "following successful / unfollow successful"
        }


## Get Discover [/following/discover{?limit}{?uid}{?page}{?country_code}{?refresh}]

### List Discover [GET]
+ Parameters

    + limit : 20 (number)
    + uid : 1 (number)
    + page : 1 (number)
    + country_code : SG (string)
    + refresh : 23123 (number) - timestamp when the page is first loaded
    
+ Response 200 (application/json)

        {
            "data" : 
            [
                {
                    
                    "product":{
                        "id":0,
                        "image":"test.jpg",
                        "status":"open",
                        "created_at":123452,
                        "updated_at":123452
                    }
                },
                {
                    "product":{
                        "id":1,
                        "image":"test.jpg",
                        "status":"open",
                        "created_at":123452,
                        "updated_at":123452
                    }
                },
                {
                    "product":{
                        "id":2,
                        "image":"test.jpg",
                        "status":"open",
                        "created_at":123452,
                        "updated_at":123452
                    }
                }
            ],
            "limit" : 20,
            "page" : 1
        }

## Get Recommended [/following/recommended{?limit}{?uid}{?page}{?country_code}{?language_code}{?refresh}]
### List Recommended [GET]

+ Parameters

    + limit : 20 (number)
    + uid : 1 (number)
    + page : 1 (number)
    + country_code : SG (string)
    + language_code : EN (string)
    + refresh : 1232 (number) - timestamp when the page is first loaded 
    
+ Response 200 (application/json)

        {
            "data" : 
            [
                {
                    "type":"spotlight",
                    "type_label":"recommended by",
                    "followee_uid":0,
                    "seller":{
                        "uid":2,
                        "nickname" : "test 2",
                        "avatar" : "test2.jpg",
                        "items_count":10
                    },
                    "product" : [
                        {
                            "id":0,
                            "image":"test.jpg",
                            "status":"open",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":1,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":2,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":3,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":4,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        }
                    ]
                },
                {
                    "type":"liked",
                    "type_label":"based on you liked",
                    "followee_uid":0,
                    "seller":{
                        "uid":2,
                        "nickname" : "test 2",
                        "avatar" : "test2.jpg",
                        "items_count":10
                    },
                    "product" : [
                        {
                            "id":0,
                            "image":"test.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":1,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":2,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":3,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":4,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        }
                    ]
                },
                {
                    "type":"followee",
                    "type_label":"recommended by",
                    "followee_uid":0,
                    "seller":{
                        "uid":2,
                        "nickname" : "test 2",
                        "avatar" : "test2.jpg",
                        "items_count":10
                    },
                    "product" : [
                        {
                            "id":0,
                            "image":"test.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":1,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":2,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":3,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        },
                        {
                            "id":4,
                            "image":"test1.jpg",
                            "created_at":123452,
                            "updated_at":123452
                        }
                    ]
                }
                
            ],
            "limit" : 20,
            "page" : 1
        }

## Get Following [/following/feed/{?limit}{?uid}{?page}{?country_code}]
### List Following Feed [GET]

+ Parameters

    + limit : 20 (number)
    + uid : 1 (number)
    + page : 1 (number)
    + country_code : SG (string)
    
+ Response 200 (application/json)

        {
            "data" : 
            [
                {
                    "seller":{
                        "uid":2,
                        "nickname" : "test 2",
                        "avatar" : "test2.jpg"
                    },
                    "product" : {
                        "id":0,
                        "image":"test.jpg",
                        "title":"women leather",
                        "brand_name":"PRADA",
                        "likes_count":0,
                        "comments_count":0,
                        "liked":true,
                        "commented":true,
                        "currency_code":"SGD",
                        "description":"test",
                        "status":"open",
                        "selling_price":123.5,
                        "country_code":"SG",
                        "created_at":123452,
                        "updated_at":123452
                    }
                }
            ],
            "limit" : 20,
            "page" : 1
        }
