{
private void btnCalculate_Click(object sender, EventArgs e)
{
   
    string num1Text = txtNum1.Text;
    string num2Text = txtNum2.Text;
    string symbolText = lblSymbol.Text;

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

    double num1 = double.Parse(num1Text);
    double num2 = double.Parse(num2Text);

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

    lblResult.Text = result.ToString();
}

private void btnPlus_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "+";
}

private void btnMinus_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "-";
}

private void btnMultiply_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "*";
}

private void btnDivide_Click(object sender, EventArgs e)
{
    lblSymbol.Text = "/";
}
}
