## TEST PLAN

| TEST ID  |  TEST CASE OBJECTIVE| INPUT DATA | EXPECTED OUTPUT| ACTUAL OUTPUT| STATUS |
|----------|---------------------|------------|----------------|--------------|--------|
|   TC_01  |    send_a_string    |    PIN0    |       1        |      1       |  PASS  |        
|   TC_02  |    send_a_string    |    PIN0    |       1        |      -       |  FAIL  |     
|   TC_03  |    send_a_string    |    PIN1    |       2        |      2       |  PASS  |     
|   TC_04  |    send_a_string    |    PIN1    |       2        |      -       |  FAIL  |     
|   TC_05  |    send_a_string    |    PIN2    |       3        |      3       |  PASS  |     
|   TC_06  |    send_a_string    |    PIN2    |       3        |      -       |  FAIL  |     
|   TC_07  |    send_a_string    |    PIN3    |       4        |      4       |  PASS  |     
|   TC_08  |    send_a_string    |    PIN3    |       4        |      -       |  Fail  |  
|   TC_09  |    send_a_string    |    PIN4    |       5        |      5       |  PASS  |  
|   TC_10  |    send_a_string    |    PIN4    |       5        |      -       |  Fail  |  
|   TC_11  |    send_a_string    |    PIN5    |       6        |      6       |  PASS  | 
|   TC_12  |    send_a_string    |    PIN5    |       6        |      -       |  FAIL  |
|   TC_13  |    send_a_string    |    PIN6    |       7        |      7       |  PASS  | 
|   TC_14  |    send_a_string    |    PIN6    |       7        |      -       |  Fail  |     
|   TC_15  |    send_a_string    |    PIN7    |       8        |      8       |  PASS  |   
|   TC_16  |    send_a_string    |    PIN7    |       8        |      -       |  FAIL  |
|   TC_17  |    send_a_string    |    PIN8    |       9        |      9       |  PASS  |     
|   TC_18  |    send_a_string    |    PIN8    |       9        |      -       |  Fail  |     
|   TC_19  |   send_a_command    |   1<<RS    |     SEND       |    SEND      |  PASS  | 
|   TC_20  |   send_a_command    |   1<<RS    |     SEND       |      -       |  FAIL  | 
|   TC_21  |   send_a_command    |    1<<E    |    RECEIVE     |   RECEIVE    |  PASS  | 
|   TC_22  |   send_a_command    |    1<<E    |    RECEIVE     |      -       |  FAIL  | 
