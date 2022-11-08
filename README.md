# customHook
Instead of using same data in different components use custom hook - for reusing the data. 



update file useconter to 
import { useState, useEffect } from "react";
const useCounter= (forwards = true)=>{
    const [counter, setCounter] = useState(0);
    useEffect(()=>{
        const interval= setInterval(()=>{
            if(forwards){
            setCounter(prevCount=>prevCount+1);
        }else{
            setCounter(prevCount=>prevCount-1);
        }
        }
         ,1000); return ()=>clearInterval(interval);
     },[forwards])
     return counter;
}

export default useCounter
