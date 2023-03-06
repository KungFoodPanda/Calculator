# Calculator
Calculator
//
private void btnCalculate_Click(object sender, EventArgs e)
{
    // Get the numbers and symbol from the textboxes and label
    string num1Text = txtNum1.Text;
    string num2Text = txtNum2.Text;
    string symbolText = lblSymbol.Text;

    // Check if the numbers contain a symbol
    if (num1Text.Contains("+") || num1Text.Contains("-") || num1Text.Contains("*") || num1Text.Contains("/"))
    {
        MessageBox.Show("Number 1 contains a symbol!", "Error");
        return;
    }
    if (num2Text.Contains("+") || num2Text.Contains("-") || num2Text.Contains("*") || num2Text.Contains("/"))
    {
        MessageBox.Show("Number 2 contains a symbol!", "Error");
        return;
    }

    // Convert the numbers to doubles
    double num1 = double.Parse(num1Text);
    double num2 = double.Parse(num2Text);

    // Calculate the result based on the symbol
    double result = 0;
    switch (symbolText)
    {
        case "+":
            result = num1 + num2;
            break;
        case "-":
            result = num1 - num2;
            break;
        case "*":
            result = num1 * num2;
            break;
        case "/":
            result = num1 / num2;
            break;
        default:
            MessageBox.Show("Invalid symbol!", "Error");
            return;
    }

    // Display the result
    lblResult.Text = result.ToString();
}

// Set the symbol label to "+" when the "+" button is clicked
private void btnPlus_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "+";
}

// Set the symbol label to "-" when the "-" button is clicked
private void btnMinus_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "-";
}

// Set the symbol label to "*" when the "*" button is clicked
private void btnMultiply_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "*";
}

// Set the symbol label to "/" when the "/" button is clicked
private void btnDivide_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "/";
}
//
