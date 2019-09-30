# Handle-API-Json-reponse-
These methods will help to handle json response ,for Strings, Dictionary , Array from API reponse .


```swift
    //MARK:- Handle Json response
    //MARK:
    
    //For String type key Value
    func checkForString(key : String,dict : NSDictionary) -> String{
        if let str = dict.value(forKey: key){
            if str is String{
                let myStr = str as! String
                return myStr.trimmingCharacters(in: .whitespacesAndNewlines)
            }else{
                return "\(str)"
            }
            
        }else{
            return ""
        }
    }
    
    //For Bool Type Key Value
    func checkForBool(key : String,dict : NSDictionary) -> Bool{
        if let value = dict.value(forKey: key) as? Bool {
            if value is Bool && value  == true{
                return true
            }else{
                return false
            }
            
        }else{
            return false
        }
    }
    
    //For array type key value
    func checkForArr(key : String,dict : NSDictionary) -> NSMutableArray{
        
        if let arr = dict.value(forKey: key){
            if arr is NSArray{
                return NSMutableArray(array: arr as! [AnyObject])
            }else{
                return NSMutableArray()
            }
        }else{
            return NSMutableArray()
        }
    }
    
    //For dictionary type key value
    func checkForDict(key : String,dict : NSDictionary) -> NSMutableDictionary{
        if let myDict = dict.value(forKey: key){
            if myDict is NSDictionary{
                return  NSMutableDictionary(dictionary: myDict as! [NSObject : AnyObject])
            }else{
                return NSMutableDictionary()
            }
        }else{
            return NSMutableDictionary()
        }
    }

```
