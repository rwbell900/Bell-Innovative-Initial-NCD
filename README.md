# Rust Smart Contract a Wholesale Destributor and His Inventory and Orders and their status
###########################################################################################

  Background and description
  ##########################
  This is the demo for my Certified Near Developer and a foundation to build on
  Going forward.
  In the long-run this contract will be accessed by two different e-commerce front
  end websites. 
  1.  The application portal for a Manufacturer that in this example manufactures
      Bags and cases of bags of product.  My familly has an interest in a company XtraGrow LLC
      That makes an OMRI listed soil enhancement product.  Web site www.xtragrow.com
      This is the product that I have in mind for the first test case.
  2.  The e-commerce for a wholesale destributor that sells the product in this example on
      their website and pre-purchases inventory that is held by the manufacturer and drop shipped
      to customers of the wholesale destributor by the manufacturer based on orders added to the contract.

  Example scenerio
  ################ 
  1.  The wholesale destributor first applies for a destributor account with the manufacturer via the 
      manufacturers website.  The contract is deployed with the wholesale destributor contract with a status of 
      "Applicant".
  2.  The manufacturer then approves the wholesale destributor as a destributor for the manufacturer.  The
      Status is then changed to "Approved".
  3.  The wholesale destributor then purchases inventory of bags and cases of product that the manufacturer    
      can hold and drop-ship as orders are made from the wholesale destributors website.
  4.  Orders are then placed on the wholesale destributors website and paid for either in NEAR or by 
      credit card" payment. This will be implemented in a later version of this contract.
  5.  The order is then added to the list of orders for the wholesale destributor.  The status of the order at that 
      time will be "ordered".
  6.  The manufacturer then drop-ships the order to the address on the order that was added to the contract.
  7.  The status of the order is then updated to "Shipped".
  8.  Additional status changes for tracking delivery of the product can also be added to the order record.
  9.  In future versions of this contract I invision adding a "Factory" contract and adding a collection of 
      wholesale destributors to this contract, or creating multiple instances of this contract that exist only as long as the wholesale customer/distributor is active.
  10. The unit test for this contract creates the contract puts the wholesale destributor in "Applicant" status, 
      updates them to "Approved" status then adds an order to the order list.  Also all get and set methods are tested in addition to an encription method for storing account information encripted.  Then verifying that the account Id matches the encripted value stored.

FINALLY

I have used all of the functionality requested in the Certified Near Developer outline for a demo.

The following shell scripts are provided and can be used either with bash or sh.
The following environment variables are required for the following shell scripts.

Environment Variables that need to be set before using scripts:
###############################################################
Export CONTRACTS = Contract name assigned by deployment
Export OWNER = Account controled by you

Scripts Provided
################
1.  dev-deploy.sh  -- cleans up, builds release version of contract and deploy's contract on near environment
2.  dev-cleanup.sh  -- cleans up the development files and previous contract deployment without re-deploying contract.
3.  test.sh -- builds contract and runs the Unit test modules
4.  build.sh -- builds the project and moves the wasm file into the res directory