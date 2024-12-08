# Firebase onAuthStateChanged Unsubscribe Issue
This repository demonstrates a common issue with the Firebase `onAuthStateChanged` listener: improper unsubscription, leading to potential memory leaks. The original code lacks a proper cleanup mechanism when the component unmounts, while the solution shows how to correctly unsubscribe using useEffect hook. 

## Problem
The `onAuthStateChanged` listener continuously listens for authentication state changes. Without proper cleanup, this listener remains active even after the component is unmounted, potentially leading to memory leaks and unexpected behavior. 

## Solution
The solution uses the useEffect hook to ensure that the listener is unsubscribed when the component unmounts. The return function within useEffect acts as a cleanup function, executing the unsubscribe function before the component is destroyed.