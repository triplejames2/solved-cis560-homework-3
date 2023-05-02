Download Link: https://assignmentchef.com/product/solved-cis560-homework-3
<br>
Submit a query for each of the following questions. All queries will be solutions against the <strong>WideWorldlmporters </strong>database. The questions make specific request regarding implementation requirements, but you may need additional constructs as well. For example, if the question is asking for a correlated subquery to calculate a required field, you may also need joins in your solution.

<strong>Question 1</strong>

<strong>10 points </strong><strong>– </strong>Write a query to return all orders from January 2016 placed by customers in the “Computer Store” category. Your solution should use a self-contained subquery to identify the customers belonging to the “Computer Store” category.

<strong>Required Tables</strong>

<ul>

 <li>CustomerCategories</li>

 <li>Customers</li>

 <li>Orders</li>

 <li>OrderLines</li>

</ul>

<strong>Result Columns</strong>

<ul>

 <li><strong>OrderlD </strong><strong>— </strong>Identifier of the order as it exists in <em>Orders.</em></li>

 <li><strong>OrderDate </strong><strong>— </strong>The date of the order as it exists in <em> Orders.</em></li>

 <li><strong>CustomerlD </strong><strong>— </strong>The identifier of the customer placing the order.</li>

 <li><strong>OrderTotal </strong><strong>— </strong>The total for the order calculated using the <em>Quantity </em>and <em>UnitPrice </em>from <em>OrderLines.</em></li>

</ul>

The results should be sorted with the highest order total first, then by <em>OrderlD </em>in ascending order to make the results deterministic. <strong>Partial Results</strong>

With the correct solution, the first two rows should be as follows:

<strong>OrderlD OrderDate CustomerlD OrderTotal</strong>

<table>

 <tbody>

  <tr>

   <td width="57">64519</td>

   <td width="88">2016-01-08</td>

   <td width="68">1036</td>

   <td width="772">18405.00</td>

  </tr>

  <tr>

   <td width="57">65309</td>

   <td width="88">2016-01-21</td>

   <td width="68">1055</td>

   <td width="772">12643.00</td>

  </tr>

 </tbody>

</table>




<strong>11/12/2018                                                                                                                                          </strong><strong>Homework 3</strong>

<strong>Question </strong><strong>2</strong>

<strong>10 points </strong><strong>– </strong><strong>Write a query to return suppliers from the category of “Novelty Goods Supplier” for which no stock items are kept. Your solution should use a correlated subquery to indicate whether a given supplier has stock items.</strong>

<strong>Required Tables</strong>

<ul>

 <li><strong>SupplierCategories</strong></li>

 <li><strong>Suppliers</strong></li>

 <li><strong>Stockltems</strong></li>

 <li><strong>Cities</strong></li>

 <li><strong>StateProvinces</strong></li>

</ul>

<strong>Result Columns</strong>

<ul>

 <li><strong>SupplierlD </strong><strong>— </strong><strong>Identifier of the supplier as it exists in <em>Suppliers.</em></strong></li>

 <li><strong>SupplierName </strong><strong>— </strong><strong>Name of the supplier as it exists in <em>Suppliers.</em></strong></li>

 <li><strong>City </strong><strong>— </strong><strong>Name of the postal city of the supplier as it appears in <em>CityName </em>of <em>Cities.</em></strong></li>

 <li><strong>State </strong><strong>— </strong><strong>Postal state of the supplier as it appears in <em>StateProviceCode </em>of <em>StateProvinces </em>for the postal city.</strong></li>

 <li><strong>PostalCode </strong><strong>— </strong><strong>As it appears in the <em>PostalPostalCode </em>of <em> Suppliers.</em></strong></li>

</ul>

<strong>The results should be sorted by supplier name in ascending order.</strong>

<strong>Partial Results</strong>

<strong>With the correct solution, the first row should be as follows:</strong>

<strong>SupplierlD              </strong><strong>SupplierName                         </strong><strong>City                           </strong><strong>State PostalCode</strong>

<strong>8                          Lucerne Publishing                Jonesborough         TN          37659</strong>

<strong>Question </strong><strong>3</strong>

<strong>10 </strong><strong>points </strong><strong>– </strong><strong>Write a query that returns all orders for customer with a CustomerlD of </strong><strong>90, </strong><strong>along with the order total and number of days since the customer’s previous order. </strong><strong>You should use a correlated subquery to calculate the number of days since the previous order.</strong>

<strong>Required Tables</strong>

<ul>

 <li><strong>Orders</strong></li>

 <li><strong>OrderLines</strong></li>

</ul>

<strong>Result Columns</strong>

<ul>

 <li><strong>OrderlD </strong><strong>— </strong><strong>Identifier of the order as it exists in <em>Orders.</em></strong></li>

 <li><strong>OrderDate </strong><strong>— </strong><strong>The date of the order as it exists in <em> Orders.</em></strong></li>

</ul>

11/12/2018                                                                                                                                                                                          Homework 3

<ul>

 <li><strong>OrderTotal — </strong>The total for the order calculated using the <em>Quantity </em>and <em>UnitPrice </em>from <em>OrderLines.</em></li>

 <li><strong>DaysSincePreviousOrder — </strong>The days since the previous order for the customer. In addition to using a correlated subquery, you should use the<strong><u> DATEDIFF </u></strong><strong><u>(</u></strong><a href="https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql)"><strong>https://docs.microsoft.com/en-us/sql/t-sql/functions/datediff-transact-sql)</strong></a> Its first argument should be <em>DAY. </em>The second argument would be the earliest of the two dates compared, which in our case is the date of the previous order. The third argument would be the row’s order date, which would be <em>OrderDate </em>from <em>Sales.Orders.</em></li>

 <li>The results should be sorted by <em>OrderlD </em>in ascending order.</li>

</ul>

<strong>Partial Results</strong>

With the correct solution, the first two rows should be as follows:

<table>

 <tbody>

  <tr>

   <td width="68"><strong>OrderlD</strong></td>

   <td width="81"><strong>OrderDate</strong></td>

   <td width="75"><strong>OrderTotal</strong></td>

   <td width="761"><strong>DaysSincePreviousOrder</strong></td>

  </tr>

  <tr>

   <td width="68">1455</td>

   <td width="81">2013-01-29</td>

   <td width="75">365.00</td>

   <td width="761">NULL</td>

  </tr>

  <tr>

   <td width="68">1890</td>

   <td width="81">2013-02-06</td>

   <td width="75">915.00</td>

   <td width="761">8</td>

  </tr>

 </tbody>

</table>




<strong>Question 4</strong>

<strong>10 </strong><strong>points – </strong>Write a query to return sales information for each customer who placed an order in 2015. Your solution should use a derived table to calculate the <em>OrderCount </em>and <em>Sales </em>for each <em>CustomerlD. </em><strong>Required Tables</strong>

<ul>

 <li>Customers</li>

 <li>Orders</li>

 <li>OrderLines</li>

</ul>

<strong>Result Columns</strong>

<ul>

 <li><strong>CustomerlD — </strong>Identifier of the customer as it exists in <em>Customers.</em></li>

 <li><strong>CustomerName — </strong>The name of the customer as it exists in <em>Customers.</em></li>

 <li><strong>OrderCount — </strong>The number of orders place in 2015 by each customer.</li>

 <li><strong>Sales — </strong>The total sales for each customer in 2015. Sales are calculated using the <em>Quantity </em>and <em>UnitPrice </em>from <em>OrderLines.</em></li>

</ul>

The results should be sorted with the customer having the highest sales first, then by <em>CustomerlD </em>in ascending order to make the results deterministic. <strong>Partial Results</strong>

With the correct solution, the first two rows should be as follows:

<table>

 <tbody>

  <tr>

   <td width="94"><strong>CustomerlD</strong></td>

   <td width="123"><strong>CustomerName</strong></td>

   <td width="98"><strong>OrderCount</strong></td>

   <td width="670"><strong>Sales</strong></td>

  </tr>

  <tr>

   <td width="94">820</td>

   <td width="123">Knut Svensson</td>

   <td width="98">55</td>

   <td width="670">150701.50</td>

  </tr>

  <tr>

   <td width="94">996</td>

   <td width="123">Laszlo Gardenier</td>

   <td width="98">38</td>

   <td width="670">150506.70</td>

  </tr>

 </tbody>

</table>




<strong>Question 5</strong>




11/12/2018                                                                                                                                                                                          Homework 3

<strong>10 points </strong><strong>– </strong>Use the same requirements as with <u>Question 4</u> and write another query using a common table expression rather than a derived table to calculate the <em>OrderCount </em>and <em>Sales </em>for each <em>CustomerlD. </em>The results should be equivalent to those in <u>Question 4.</u>

<strong>Submission</strong>

Please submit your solution to each question in a single SQL file clearly marking each question with a comment line, or each in a separate file with a file name clearly indicating the question it solves. Include a comment line above each solution indicating which question it answers. Please do not submit your results, only the SQL solutions.

<strong>Five Questions – 10 Each</strong>


