# test-gas
test app script
function myFunction() {
  
  var lookupValue1 = "Status";
  var lookupValue2 = "Open";
  var ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  
  var lc = ss.getLastColumn();
  
  var lr = ss.getLastRow();
  
  var loolupRangeValues1 = ss.getRange(1, 1, 1, lc).getValues()[0]; // Get column name
  
  var columneName = loolupRangeValues1.indexOf(lookupValue1) + 1; // Get Status column position
  
  var loolupRangeValues3 = ss.getRange(2, columneName, lr - 1).getValues(); // Get all values in Status column

  Logger.log(loolupRangeValues3); 
  
  for(var i = 0; i < lr; i++) {
      if(loolupRangeValues3[i] == "Open"){
        row = loolupRangeValues3[i];
        Logger.log(row);
        Logger.log(i+1); // Get row number of bug with Open status
      }
        else if(loolupRangeValues3[i] == "Resolved"){
          row = loolupRangeValues3[i];
          Logger.log(row);
          Logger.log(i+1); // Get row number of bug with Resolved status
      }
  }
  
}
