<!-- Login.aspx -->
<form id="loginForm" runat="server">
<div>
<label for="username">Username:</label>
<asp:TextBox ID="username" runat="server"></asp:TextBox>
 <br />
<label for="password">Password:</label>
<asp:TextBox ID="password" TextMode="Password" runat="server"></asp:TextBox>
<br />
 <asp:Button ID="loginButton" Text="Login" OnClick="Login_Click" runat="server" />
 </div>
</form>

<!-- EmployeeInfo.aspx -->
<form id="employeeForm" runat="server">
<div>
<label for="employeeId">Employee ID:</label>
<asp:TextBox ID="employeeId" runat="server"></asp:TextBox>
<asp:Button ID="searchButton" Text="Search" OnClick="Search_Click" runat="server" />
<br />
<!-- Display employee information here -->
<br />
<label for="firstName">First Name:</label>
<asp:TextBox ID="firstName" runat="server"></asp:TextBox>
<br />
<label for="lastName">Last Name:</label>
<asp:TextBox ID="lastName" runat="server"></asp:TextBox>
<br />
<asp:Button ID="updateButton" Text="Update" OnClick="Update_Click" runat="server" />
</div>
</form>
// Login.aspx.cs
protected void Login_Click(object sender, EventArgs e)
{
    string username = this.username.Text;
    string password = this.password.Text;

    // Validate login credentials against database
    if (ValidateLogin(username, password))
    {
        // Redirect to Employee Information Page
        Response.Redirect("EmployeeInfo.aspx");
    }
    else
    {
        // Display error message
        // For simplicity, display error message directly on the page
        // You should implement proper error handling and display
        Response.Write("<script>alert('Invalid username or password');</script>");
    }
}

private bool ValidateLogin(string username, string password)
{
    // Implement logic to validate login credentials against database
    // Example:
    // Check if username and password exist in Logins table
    // Return true if valid, false otherwise
    return true; // Placeholder for demo
}

// EmployeeInfo.aspx.cs
protected void Search_Click(object sender, EventArgs e)
{
    string employeeId = this.employeeId.Text;

    // Retrieve employee information from database based on employeeId
    // Populate TextBoxes with employee information
    // Example:
    // this.firstName.Text = // Retrieve first name from database
    // this.lastName.Text = // Retrieve last name from database
}

protected void Update_Click(object sender, EventArgs e)
{
    // Update employee information in database based on changes made by admin
    // Example:
    // string employeeId = this.employeeId.Text;
    // string firstName = this.firstName.Text;
    // string lastName = this.lastName.Text;
    // Update employee record in Employees table
}

