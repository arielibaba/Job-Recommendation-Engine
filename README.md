# Job-Recommendation-Engine
This project aims to create a job referential that will be used by recruiters to recommend jobs to jobseekers.
<br>
<br>
### Context
In the temporary work industry, and more generally in recruitment, knowledge of the relationship between the jobs is a considerable advantage in improving the staffing process.
Indeed, being able to say that job A is equivalent to job B or that job A requires similar skills to those of job B, for example, makes it possible to
to propose a profile that has practised job B for an offer in job A.

The aim here will be to create a job referential by determining the similarities between the various jobs.
For example, a graph of jobs could be defined: the nodes of this graph would be the jobs, while each of the edges would represent the distance between them.
Then, following this, clusters of "similar" jobs can be deduced.

**The data:**<br>
To build this referential, you have the history of all the Gojob applications (~324k lines).

With in columns :<br>
*worker_id | order_id | list_profession_3 | list_profession_2 | order_prof_3 |order_prof_2*

Where:<br>
- *worker_id*: the unique id of our registrants
- *order_id*: the unique id of the job offers
- *list_profession_3*: the declared list of level 3 jobs practised by the registrant
- *list_profession_2*: the declared list of level 2 jobs practiced by the registrant
- *order_list_profession_2*: the list of level 2 jobs and related occupations in the offer
- *order_list_profession_3*: the list of jobs and related occupations at level 3 of the offer

nb: the job levels correspond to our categorisation of jobs. We have 3
levels, 1, 2 and 3:<br>
→ *Level 1* is very general, and includes about ten elements (Industry,Agriculture, Services etc... ), and is not present in this dataset.<br>
→ *Level 2* is a little more precise, and its elements are categories of jobs (Accounting, Sales, Reception)<br>
→ *Level 3* designates the jobs as such (Accounting assistant, Accountant, Salesperson, Salesperson, Switchboard operator, Receptionist)

**Note:**<br>
We can consider several interactions between the jobs to generate this graph:<br>
→ Two jobs A and B carried out by the same person<br>
→ A job A carried out by a person applying for a job B<br>
→ Two jobs A and B required in the same offer

Another way of performing the calculation of jobs similarity could be to consider their descriptions. This way, we could use natural language processing or understanding (NLP or NLU) to achieve the same goal of grouping of the jobs. However, as the texts describing the jobs are not available in this dataset, we cannot afford to implement such an approach.

The referential will probably benefit from the analysis of these three interactions.
