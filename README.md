# Assignment-3-MongoDB-Setup-and-Queries

# Query 1
Find all movies with runtime greater than 200 minutes in year 1983.
Sort results by runtime in ascending order. Only include runtime, title, and year.

Filter documents where year equals 1983. Apply the $gt operator on runtime to select movies longer than 200 minutes.  Use projection to include only runtime, title, and year, and exclude _id.  
Sort the results in ascending order by runtime.


db.movies.find(
  { year: 1983, runtime: { $gt: 200 } },
  { runtime: 1, title: 1, year: 1}
).sort({ runtime: 1 })


<img width="446" height="500" alt="1" src="https://github.com/user-attachments/assets/0059aec0-73f2-4de7-9656-e145ce26d548" />

# Query 2
Find all movies after year 2014 with IMDb rating greater than 9.

Filter documents where year is greater than 2014 using the $gt operator. Access the nested IMDb rating field using dot notation ("imdb.rating") and filter values greater than 9. Use projection to include only title, year, and imdb rating, and exclude _id.

db.movies.find(
  { year: { $gt: 2014 }, "imdb.rating": { $gt: 9 } },
  { title: 1, year: 1, "imdb.rating": 1}
)

<img width="434" height="356" alt="2" src="https://github.com/user-attachments/assets/cbbea032-2fb2-439d-8443-5b410a027601" />
