# Testing

## Test Plan
TODO: Describe any manual and automated (unit) tests. Uniquely identify each test case. Include prerequisites and test data.

Test Runs
TODO: For each test described above, indicate the current status. 
Create a requirements traceability matrix to validate the completeness of the product.

| Use-Case ID | Requirement ID | Test Case | Status |
| ----------- | -------------- | --------- | ------ |

TODO: Add rows for each test, current status is eg. pass/fail
Use-Case ID	    Requirement ID	     Test Case	Status	Notes
UC1	             FR1,FR5	           TC-01	Pass	Full hotel   details shown
UC2	             FR3	               TC-02	Fail	Filter implementation pending
UC3	             FR4	               TC-03	Pass	Map integration complete
UC4	             FR7	               TC-04	Pass	Auth system working
UC5              NFR1	               TC-01	Pass	<2s load time observed

Manual Tests:

ID	   Test Scenario	  Test Steps	               Expected Result	                                      Actual Result	                    Status
MT01	Hotel Browsing	  1. Access homepage           Displays 4+ hotels with complete details               All hotels loaded correctly	    Pass
                          2. Click "Explore"
                          3. Select Hotels tab		
MT02	Restaurant Search 1. Navigate to Restaurants   Shows Italian Resturants                               No filtering Available            Fail
                          2. Search "Italian"          
MT03	Map Interaction	  1. Click map marker           Displays business details	                          Info shows correctly	            Pass
                          2. Verify info window	  
