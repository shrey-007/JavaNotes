### Ways of creating string
1. String Literal(normal method)
2. new keyword

### Concept
1. String pool is a memory inside heap.
2. Jab bhi 1st method se string banti hai toh pehle JVM check krta hai ki vo string already exist krti hai kya pool mai, if yes toh usi ka ek new reference bana kr de deta hai else pool mai new string banata hai and uska reference return kr deta hai
3. If 2nd method ko use krte hai toh new string bnti hai toh vo heap mai store hoti hai pool mai nhi.
4. Agar literal use kra toh object same rahega but reference aajaega naya, toh agar usne value change kri string ki toh sab ke liye change ho jaaegi that's why string is immutable.
5. There are 2 classes to create mutable strings i.e StringBuffer(Thread safe and hence slow) and StringBuilder(Not Thread safe and hence fast).

