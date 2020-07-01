# Udacity_Project_2.5_Portfolio-Exercise-Starbucks
Classification Problem

## Portfolio Exercise: Starbucks



### Background Information
The dataset in this portfolio exercise was originally used as a take-home assignment provided by Starbucks for their job candidates. The data for this exercise consists of about 120,000 data points split in a 2:1 ratio among training and test files. In the experiment simulated by the data, an advertising promotion was tested to see if it would bring more customers to purchase a specific product priced at $10. Since it costs the company 0.15 to send out each promotion, it would be best to limit that promotion only to those that are most receptive to the promotion. Each data point includes one column indicating whether or not an individual was sent a promotion for the product, and one column indicating whether or not that individual eventually purchased that product. Each individual also has seven additional features associated with them, which are provided abstractly as V1-V7.

### Optimization Strategy
My task is to use the training data to understand what patterns in V1-V7 to indicate that a promotion should be provided to a user. Specifically, my goal is to maximize the following metrics:

**Incremental Response Rate (IRR)**
IRR depicts how many more customers purchased the product with the promotion, as compared to if they didn't receive the promotion. Mathematically, it's the ratio of the number of purchasers in the promotion group to the total number of customers in the purchasers group (treatment) minus the ratio of the number of purchasers in the non-promotional group to the total number of customers in the non-promotional group (control).

![alt text](https://github.com/Tselmeg-C/Udacity_Project_2.5_Portfolio-Exercise-Starbucks/blob/master/IRR.jpg)
 
**Net Incremental Revenue (NIR)**
NIR depicts how much is made (or lost) by sending out the promotion. Mathematically, this is 10 times the total number of purchasers that received the promotion minus 0.15 times the number of promotions sent out, minus 10 times the number of purchasers who were not given the promotion.

![alt text](https://github.com/Tselmeg-C/Udacity_Project_2.5_Portfolio-Exercise-Starbucks/blob/master/NIR.jpg)
 
For a full description of what Starbucks provides to candidates see the [instructions available here](https://drive.google.com/file/d/18klca9Sef1Rs6q8DW4l7o349r8B70qXM/view).

In the repository _training.cvs_ data was explored using jupyter notebook. Open _Starbucks-Copy1.ipynb_ to see the codes.

### How To Test Strategy?
After I have an optimization strategy, I have completed the _promotion_strategy_ function to pass to the _test_results_ function.
There are four possible outomes:

Table of actual promotion vs. predicted promotion customers:

![alt text](https://github.com/Tselmeg-C/Udacity_Project_2.5_Portfolio-Exercise-Starbucks/blob/master/table_accuracy.jpg)

The metrics are only being compared for the individuals we predict should obtain the promotion – that is, quadrants I and II. Since the first set of individuals that receive the promotion (in the training set) receive it randomly, I expected that quadrants I and II will have approximately equivalent participants.

Comparing quadrant I to II then gives an idea of how well my promotion strategy will work in the future.

My IRR and NIR with my developed strategy were 0.0187 and 358.05 respectively, while the original solution (which was provided from the course designer) was with a IRR of 0.0188 and an NIR of 189.45 on the test set.
