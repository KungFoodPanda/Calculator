

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

---------------------------------------------------------------------------------
private void btnConvert_Click_Click(object sender, EventArgs e)
        {
        
            double amount = double.Parse(txtAmount.Text);
            string fromCurrency = cmbFromCurrency.SelectedItem.ToString();
            string toCurrency = cmbToCurrency.SelectedItem.ToString();

            double convertedAmount = 0;
            switch (fromCurrency)
            {
                case "Rubles":
                    if (toCurrency == "Euro")
                    {
                        convertedAmount = amount / 90; 
                    }
                    else if (toCurrency == "Dollars")
                    {
                        convertedAmount = amount / 75; 
                    }
                    break;
                case "Euro":
                    if (toCurrency == "Rubles")
                    {
                        convertedAmount = amount * 90; 
                    }
                    else if (toCurrency == "Dollars")
                    {
                        convertedAmount = amount * 1.2; 
                    }
                    break;
                case "Dollars":
                    if (toCurrency == "Rubles")
                    {
                        convertedAmount = amount * 75; 
                    }
                    else if (toCurrency == "Euro")
                    {
                        convertedAmount = amount / 1.2; 
                    }
                    break;
            }

            lblResult.Text = convertedAmount.ToString("0.00") + " " + toCurrency;
        }
