# Job-Recommendation-Engine
This project aims to create a job referential that will be used by recruiters to recommend jobs.
<br>
<br>
### Context
In the temporary work industry, and more generally in recruitment, knowledge of the relationship between the jobs is a considerable advantage in improving the staffing process.
Indeed, being able to say that job A is equivalent to job B or that job A requires similar skills to those of job B, for example, makes it possible to
to propose a profile that has practised job B for an offer in job A.

The aim here will be to create a job referential by determining the similarities between the various trades.
For example, a graph of trades could be defined: the nodes of this graph would be the jobs, while each of the edges would represent the distance between them.
Then, following this, clusters of "similar" jobs can be deduced.
<br>
**The data:**
To build this referential, you have the history of all the Gojob applications (~324k lines).

With in columns :
worker_id | order_id | list_profession_3 | list_profession_2 | order_prof_3 |order_prof_2

Where:
- worker_id: the unique id of our registrants
- order_id: the unique id of the job offers
- list_profession_3: the declared list of level 3 jobs practised by the registrant
- list_profession_2: the declared list of level 2 jobs practiced by the registrant
- order_list_profession_2: the list of level 2 jobs and related occupations in the offer
- order_list_profession_3 : the list of jobs and related occupations at level 3 of the offer

nb: the trade levels correspond to our categorisation of trades. We have 3
levels, 1, 2 and 3.
→ Level 1 is very general, and includes about ten elements (Industry,Agriculture, Services etc... ), and is not present in this dataset.
→ Level 2 is a little more precise, and its elements are categories of jobs (Accounting, Sales, Reception)
→ Level 3 designates the trades as such (Accounting assistant, Accountant, Salesperson, Salesperson, Switchboard operator, Receptionist)

**Note:**
We can consider several interactions between the jobs to generate this graph.
→ Two jobs A and B carried out by the same person
→ A job A carried out by a person applying for a job B
→ Two jobs A and B required in the same offer

The referential will probably benefit from the analysis of these three interactions.
