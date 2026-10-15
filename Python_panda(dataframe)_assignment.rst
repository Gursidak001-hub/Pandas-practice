.. code:: ipython3

    import pandas as pd
    
    data = {
        "Customer_ID": list(range(101, 121)),
        "Name": [
            "Amit", "Neha", "Rahul", "Priya", "Vikas",
            "Sneha", "Rohit", "Pooja", "Karan", "Anjali",
            "Manish", "Simran", "Deepak", "Riya", "Arjun",
            "Kavita", "Nitin", "Meena", "Varun", "Isha"
        ],
        "Age": [
            25, 32, 45, 28, 51, 36, 23, 42, 31, 29,
            55, 38, 47, 26, 34, 49, 40, 30, 44, 27
        ],
        "Gender": [
            "Male", "Female", "Male", "Female", "Male",
            "Female", "Male", "Female", "Male", "Female",
            "Male", "Female", "Male", "Female", "Male",
            "Female", "Male", "Female", "Male", "Female"
        ],
        "City": [
            "Delhi", "Mumbai", "Delhi", "Pune", "Jaipur",
            "Mumbai", "Delhi", "Pune", "Jaipur", "Delhi",
            "Mumbai", "Pune", "Delhi", "Jaipur", "Mumbai",
            "Delhi", "Pune", "Mumbai", "Jaipur", "Delhi"
        ],
        "Account_Type": [
            "Savings", "Current", "Savings", "Savings", "Current",
            "Savings", "Current", "Savings", "Savings", "Current",
            "Savings", "Current", "Savings", "Savings", "Current",
            "Savings", "Current", "Savings", "Current", "Savings"
        ],
        "Balance": [
            25000, 60000, 45000, 18000, 90000,
            32000, 12000, 75000, 28000, 55000,
            100000, 40000, 68000, 22000, 85000,
            95000, 35000, 48000, 72000, 15000
        ],
        "Loan_Amount": [
            0, 200000, 500000, 0, 800000,
            150000, 100000, 400000, 0, 250000,
            1000000, 300000, 600000, 0, 350000,
            700000, 200000, 0, 450000, 100000
        ]
    }
    
    df = pd.DataFrame(data)
    
    print(df)
    
     

.. code:: ipython3

     #Display customers whose Balance is greater than ₹50,000.
    print(df[df["Balance"]>50000])
    


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    1           102    Neha   32  Female  Mumbai      Current    60000   
    4           105   Vikas   51    Male  Jaipur      Current    90000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    9           110  Anjali   29  Female   Delhi      Current    55000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    12          113  Deepak   47    Male   Delhi      Savings    68000   
    14          115   Arjun   34    Male  Mumbai      Current    85000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    18          119   Varun   44    Male  Jaipur      Current    72000   
    
        Loan_Amount  
    1        200000  
    4        800000  
    7        400000  
    9        250000  
    10      1000000  
    12       600000  
    14       350000  
    15       700000  
    18       450000  
    

.. code:: ipython3

    #Find customers whose Age is greater than 40.
    print(df[df["Age"]>40])
    


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    2           103   Rahul   45    Male   Delhi      Savings    45000   
    4           105   Vikas   51    Male  Jaipur      Current    90000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    12          113  Deepak   47    Male   Delhi      Savings    68000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    18          119   Varun   44    Male  Jaipur      Current    72000   
    
        Loan_Amount  
    2        500000  
    4        800000  
    7        400000  
    10      1000000  
    12       600000  
    15       700000  
    18       450000  
    

.. code:: ipython3

    #Display customers living in Delhi.
    print(df[df["City"]=="Delhi"])


.. parsed-literal::

        Customer_ID    Name  Age  Gender   City Account_Type  Balance  Loan_Amount
    0           101    Amit   25    Male  Delhi      Savings    25000            0
    2           103   Rahul   45    Male  Delhi      Savings    45000       500000
    6           107   Rohit   23    Male  Delhi      Current    12000       100000
    9           110  Anjali   29  Female  Delhi      Current    55000       250000
    12          113  Deepak   47    Male  Delhi      Savings    68000       600000
    15          116  Kavita   49  Female  Delhi      Savings    95000       700000
    19          120    Isha   27  Female  Delhi      Savings    15000       100000
    

.. code:: ipython3

    #Find customers with Account_Type equal to Savings.
    print(df[df["Account_Type"]=="Savings"])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    0           101    Amit   25    Male   Delhi      Savings    25000   
    2           103   Rahul   45    Male   Delhi      Savings    45000   
    3           104   Priya   28  Female    Pune      Savings    18000   
    5           106   Sneha   36  Female  Mumbai      Savings    32000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    8           109   Karan   31    Male  Jaipur      Savings    28000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    12          113  Deepak   47    Male   Delhi      Savings    68000   
    13          114    Riya   26  Female  Jaipur      Savings    22000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    17          118   Meena   30  Female  Mumbai      Savings    48000   
    19          120    Isha   27  Female   Delhi      Savings    15000   
    
        Loan_Amount  
    0             0  
    2        500000  
    3             0  
    5        150000  
    7        400000  
    8             0  
    10      1000000  
    12       600000  
    13            0  
    15       700000  
    17            0  
    19       100000  
    

.. code:: ipython3

    #Find customers whose Loan_Amount is greater than ₹3,00,000.
    print(df[df["Loan_Amount"]>300000])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    2           103   Rahul   45    Male   Delhi      Savings    45000   
    4           105   Vikas   51    Male  Jaipur      Current    90000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    12          113  Deepak   47    Male   Delhi      Savings    68000   
    14          115   Arjun   34    Male  Mumbai      Current    85000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    18          119   Varun   44    Male  Jaipur      Current    72000   
    
        Loan_Amount  
    2        500000  
    4        800000  
    7        400000  
    10      1000000  
    12       600000  
    14       350000  
    15       700000  
    18       450000  
    

.. code:: ipython3

    #Display female customers whose Balance is greater than ₹30,000.
    print(df[(df["Gender"]=="Female") & (df["Balance"]>30000)])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    1           102    Neha   32  Female  Mumbai      Current    60000   
    5           106   Sneha   36  Female  Mumbai      Savings    32000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    9           110  Anjali   29  Female   Delhi      Current    55000   
    11          112  Simran   38  Female    Pune      Current    40000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    17          118   Meena   30  Female  Mumbai      Savings    48000   
    
        Loan_Amount  
    1        200000  
    5        150000  
    7        400000  
    9        250000  
    11       300000  
    15       700000  
    17            0  
    

.. code:: ipython3

    #Display customers who live in Delhi AND have a balance greater than ₹50,000.
    print(df[(df["City"]=="Delhi") & (df["Balance"]>50000)])


.. parsed-literal::

        Customer_ID    Name  Age  Gender   City Account_Type  Balance  Loan_Amount
    9           110  Anjali   29  Female  Delhi      Current    55000       250000
    12          113  Deepak   47    Male  Delhi      Savings    68000       600000
    15          116  Kavita   49  Female  Delhi      Savings    95000       700000
    

.. code:: ipython3

    #Display customers who live in Mumbai OR have a balance greater than ₹80,000.
    print(df[(df["City"]=="Mumbai") | (df["Balance"]>80000)])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    1           102    Neha   32  Female  Mumbai      Current    60000   
    4           105   Vikas   51    Male  Jaipur      Current    90000   
    5           106   Sneha   36  Female  Mumbai      Savings    32000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    14          115   Arjun   34    Male  Mumbai      Current    85000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    17          118   Meena   30  Female  Mumbai      Savings    48000   
    
        Loan_Amount  
    1        200000  
    4        800000  
    5        150000  
    10      1000000  
    14       350000  
    15       700000  
    17            0  
    

.. code:: ipython3

    #Display customers whose age is between 30 and 45, inclusive.
    print(df[(df["Age"]>=30) & (df["Age"]<=45)])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    1           102    Neha   32  Female  Mumbai      Current    60000   
    2           103   Rahul   45    Male   Delhi      Savings    45000   
    5           106   Sneha   36  Female  Mumbai      Savings    32000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    8           109   Karan   31    Male  Jaipur      Savings    28000   
    11          112  Simran   38  Female    Pune      Current    40000   
    14          115   Arjun   34    Male  Mumbai      Current    85000   
    16          117   Nitin   40    Male    Pune      Current    35000   
    17          118   Meena   30  Female  Mumbai      Savings    48000   
    18          119   Varun   44    Male  Jaipur      Current    72000   
    
        Loan_Amount  
    1        200000  
    2        500000  
    5        150000  
    7        400000  
    8             0  
    11       300000  
    14       350000  
    16       200000  
    17            0  
    18       450000  
    

.. code:: ipython3

    #Display customers whose Account_Type is "Savings" AND whose Loan_Amount is greater than ₹300,000.
    print(df[(df["Account_Type"]=="Savings") & (df["Loan_Amount"]>300000)])


.. parsed-literal::

        Customer_ID    Name  Age  Gender    City Account_Type  Balance  \
    2           103   Rahul   45    Male   Delhi      Savings    45000   
    7           108   Pooja   42  Female    Pune      Savings    75000   
    10          111  Manish   55    Male  Mumbai      Savings   100000   
    12          113  Deepak   47    Male   Delhi      Savings    68000   
    15          116  Kavita   49  Female   Delhi      Savings    95000   
    
        Loan_Amount  
    2        500000  
    7        400000  
    10      1000000  
    12       600000  
    15       700000  
    

