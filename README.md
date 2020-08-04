# Learning-Optimal-transport

THE APPLICATION OF OPTIMAL TRANSPORT IN THIS PROJECT -

The concept of optimal transport deals with the mapping between two probability distribution in the most optimal way (minimising the cost). In our project, we must 
create a map between the source languages and English for which the ML model has already been developed.
The transcripts for source languages must be acquired, which would be a challenge.
We can use three solvers and distance functions between PDFs based on optimal transport: 
1.	Earth Movers Distance OT (EMD) EMD or Wasserstein distance – 
   We can use the ot library for this. A similar task was done is the problem where we had to minimise the transportation cost between bakeries and cafes.
2.	Gaussian Optimal Transport Mapping (Gaussian kernel) 
3.	Entropic Regularization OT solver (EMD-R): 
    This can be implemented by using the ot.sinkhorn method in the ot library.
    
I have solved the the problems above using the ot library.

1. In the first problem, we had to find how the bakery products are to distributed to the cafes. First ,i found out the distance function 
   between the bakery and cafe using ot.dist and the euclideam metric (which is minowski with p=2 ) . Then using the sample weights which is the production 
   the OT matrix was calculated usingthe ot.emd ( Earth mover's distance problem ). The OT matrix is visualized using ot.plot. ot.emd2 is used to find the loss.
   ot.sinkhorn solves the entropic regularization optimal transport problem and return the OT matrix. This works using the sinkhorn-knopp algorithm.
   
2. In domain adaptation problems, one assumes the existence of two distinct joint probability distributions respectively related to a source
   and a target domains. We have the source and a target group for which the support vector machine is used upon.
   Now we have optimally transported the source unto the target. To prevent overfitting we can use entropy regularization or lasso regularization.
   
3. I have converted the images to array of pixels using the PIL library. We can input these array into the ot.dist and ot.emd to get the OT matrix and loss.
   
