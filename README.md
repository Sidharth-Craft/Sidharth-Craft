**#JavaScript Code for Hide & Show Operation in Dynamics CRM 
**

function hideshowbillingcard(executionContext) 
{
    var formcontext = executionContext.getFormContext();

    var billpayedby = formContext.getAttribute("t1_billpayedby").getValue();

    // bill Payed By creditcard
    if (billpayedby == 690830000) 
    {
        formContext.getControl("t1_creditcardnumber").setVisible(true);
        formContext.getControl("t1_debitcardnumber").setVisible(false);
        formContext.getcontrol("t1_upidetails").setVisible(false);
    }
    
    // bill Payed By debitcard
    else if (billpayedby == 690830001) 
    {
        formContext.getControl("t1_debitcardnumber").setVisible(true);
        formContext.getControl("t1_creditcardnumber").setVisible(false);
        formContext.getcontrol("t1_upidetails").setVisible(false);
  
    }

    // bill Payed By UPI
    else if (billpayedby == 690830002) 
    {
        formContext.getControl("t1_upidetails").setVisible(true);
        formContext.getControl("t1_debitcardnumber").setVisible(false);
        formContext.getcontrol("t1_creditcardnumber").setVisible(false);

    }

    else 
    {
        formContext.getControl("t1_creditcardnumber").setVisible(false);
        formContext.getControl("t1_debitcardnumber").setVisible(false);
        formContext.getControl("t1_upidetails").setVisible(false);
    }
}

function hideShowCardTypeLanguages(executionContext)

{
     var formContext = executionContext.getFormContext();

     var cardType = formContext.getAttribute("t1_cardType").getValue();

// cardtype equal to Visa
     
     if (cardType == 603004510) 
 {
   formContext.getControl("t1_cardType").setVisible(true);
 }
     else 
 {
   formContext.getControl("t1_cardType").setVisible(false);
 }

}

