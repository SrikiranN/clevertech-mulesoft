# MuleSoft challenge

This challenge consists of implementing the incomplete flows in the project and adjust the project to meet best practices.
Both have to be created in the same project using Anypoint Studio, the IDE for Mule ESB (https://developer.mulesoft.com/). 
You can download it from https://www.mulesoft.com/lp/dl/studio. 
Make sure you use Anypoint Studio 7 and Mule 4.

# Tips
* Explore the MUnit flows as these will help validate your implementation (E.g: Input and Output data).
* Feel free to adjust the project to meet best practices and standards to take the most out of the MuleSoft components.
* RAML/APIToolKit, Error handling, Metadata, Logs, MUnit will be considered as part of the final score.

# Format
* This assessment must be delivered within 2 days.
* If you wish, you can provide a IMPL.txt (plain text) or a IMPL.md (Markdown) file at the root of your repository, explaining:
    * Any comments regarding your implementation.
    * Mention anything that was asked but not delivered and why.
* Assessment goes around the success of the MUnit tests and then a manual review takes place. Make sure your packed code compiles.
* Deliver the project as a JAR file and make sure it can be open in Anypoint Studio with no issues.
* Any questions, please send an email to your recruiter.

### Flows ###

#1 - countryFlow

 * Summary: Read a record from a file based on an URI parameter, call a REST enpoint and return the expected response
 * URI Params: countryID
 * Resources: resources/endpoints/country/country.csv
 * REST: https://restcountries.eu/rest/v2/alpha/{code}

#2 - currencyFlow

 * Summary: Call two SOAP endpoints based on the query parameters and return the expected response
 * Query Params: currency, date
 * SOAP: http://currencyconverter.kowabunga.net/converter.asmx (GetCurrencyRate, GetCultureInfo)

#3 - employeeFlow

 * Summary: Load an in-memory database, query it based on the query params and return the expected response
 * Query Params: country, ageGroup, worldRank
 * Resources: resources/endpoints/employee/employee.sql
 * Query Details: 
	* age_group: 
		* age between 18 and 21 = A
		* age between 22 and 25 = B
		* age between 26 and 29 = C
		* age greater than 29   = D
		* otherwise             = ?		
	* country_rank: ordinal position of the employee according to his/her salary in comparison to other employee's salary on the same country
	* country_salary_percent: % of the employee salary in comparison to the sum of all employee's salary on the same country (format: 2 decimals + %)
	* world_rank: ordinal position of the employee according to his/her salary over the whole database  
 * In-Memory Database: http://www.h2database.com/html/main.html
 * Tip: INIT statement may be useful in a jdbc connection url

#4 - sortFlow

 * Summary: Sort an array of numbers based on the query param by using Java or other scripting language and return the expected response
 * Query Params: inputArray  

Thank you,
Clevertech Team
