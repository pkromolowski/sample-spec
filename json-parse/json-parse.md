## json-parse COBOL Application Documentation

### 1. Overview

This COBOL application demonstrates how to parse JSON data using IBM Enterprise COBOL. It reads a predefined JSON string, parses it, and displays the extracted data.

### 2. Package/module name

`json_parse`

### 3. Class/file name

`json_parse.cbl`

### 4. Detailed Documentation

#### 4.1 Procedure Division

This section contains the main logic of the program.

- **Initialization:**
    - `Initialize jtxt-1208 all value.` : Initializes a variable `jtxt-1208` which will hold the JSON string.
- **JSON Parsing:**
    - `Move function display-of(function national-of(jtxt-1047-client-data) 1208) to jtxt-1208(1:function length(jtxt-1047-client-data)).`: This line constructs the JSON string by concatenating data from a structure `jtxt-1047-client-data`.
    - `Json parse jtxt-1208 into client-data with detail suppress transactions not on exception display "Successful JSON Parse" end-json.`: This line parses the JSON string stored in `jtxt-1208` into the `client-data` structure. The `with detail` clause provides detailed information about the parsing process, `suppress transactions` prevents the creation of transaction records, and `not on exception` ensures that the program continues execution even if an error occurs during parsing.
- **Data Display:**
    - The program then displays various client information extracted from the parsed JSON data, including account number, balance, and billing information.

- **Transaction Parsing:**
    - `Move 2 to txnum.`: Sets a counter variable `txnum` to 2.
    - `Initialize jtxt-1208 all value.`: Initializes `jtxt-1208` again.
    - `Move function display-of(function national-of(jtxt-1047-transactions) 1208) to jtxt-1208(1:function length(jtxt-1047-transactions)).`: Constructs a JSON string from `jtxt-1047-transactions` data.
    - `Json parse jtxt-1208 into transactions with detail name tx-price is 'tx-priceinUS$' not on exception display "Successful JSON Parse" end-json.`: Parses the JSON string into the `transactions` structure. The `name tx-price is 'tx-priceinUS$'` clause specifies that the field named "tx-priceinUS$" should be mapped to the field named "tx-price".

- **Transaction Display:**
    - The program displays transaction details for the first two records, including TXID, description, item ID, price, and comment.

### 5. Pseudo Code

```
// Initialize variables
Initialize jtxt-1208
Move JSON string to jtxt-1208

// Parse JSON into client-data structure
Json parse jtxt-1208 into client-data with detail suppress transactions not on exception
    Display "Successful JSON Parse"

// Display client information
Display "Account Number:"
Display client-data.account-num
Display "Balance:"
Display client-data.balance
Display "Client Information: "
Display client-data.name-last
Display client-data.name-first
Display "  Address:"
Display client-data.addr-street
Display client-data.addr-city
Display client-data.addr-region
Display client-data.addr-code

// Parse JSON into transactions structure
Move 2 to txnum
Initialize jtxt-1208
Move JSON string to jtxt-1208
Json parse jtxt-1208 into transactions with detail name tx-price is 'tx-priceinUS$' not on exception
    Display "Successful JSON Parse"

// Display transaction details
Display "Transactions:"
Display "  Record 1:"
Display "    TXID:        " transactions(1).tx-uid
Display "    Description: " transactions(1).tx-item-desc
Display "    Item ID:     " transactions(1).tx-item-uid
Display "    Price:       " transactions(1).tx-price
Display "    Comment:     " transactions(1).tx-comment
Display "  Record 2:"
Display "    TXID:        " transactions(2).tx-uid
Display "    Description: " transactions(2).tx-item-desc
Display "    Item ID:     " transactions(2).tx-item-uid
Display "    Price:       " transactions(2).tx-price
Display "    Comment:     " transactions(2).tx-comment

// End of program
Goback.
```

**Note:** This pseudo code assumes a basic understanding of COBOL syntax and data structures.



