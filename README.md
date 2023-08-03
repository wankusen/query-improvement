1. Purpose: These are a SQL query that produces a search result. The query produces results in approximately 8 seconds. 
2. Task: Please suggest what improvements should be done to the query in order to improve its performance. 
   ![Uploading image.png…]()


3. Suggestion and idea
    1)	Normally the first that need to do is a check indexing, need to implement indexing for each column searching and also order by   
        column
    2)	In order to increase performance , it is possible if system limit the search column item  because this query have more than 20 
        column for searching. 
    3)	Avoid system capture all column searching, just add only column needed by user, because to many like expression with leading 
        wildcard make effect the performance
    4)	Table Information
        Table display needed : Jobs, JobCategories, JobTypes

        Table join : Jobs,JobsPersonalities, Personalities, JobsPracticalSkills, PracticalSkills, JobsBasicAbilities, BasicAbilities,            JobsTools, Tools, JobsCareerPaths, CareerPaths, JobsRecQualifications, RecQualifications, JobsReqQualifications, 
        ReqQualifications, JobCategories, JobTypes

        Table Where : JobCategories, JobTypes, Jobs, Personalities, PracticalSkills, BasicAbilities, Tools, CareerPaths, 
        RecQualifications, ReqQualifications

        Note : Because table display needed is from three table only, maybe can 
        -	create stored procedure to control only add on table join based on searching/where process table needed
        -	search focus on three table display needed
        -	get the result first from table Personalities, PracticalSkills, BasicAbilities, Tools, CareerPaths, RecQualifications, 
        ReqQualifications to avoid many selected row data display in query and combine with  the main query 
