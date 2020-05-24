contract americannetworks{
    // phone bill collection contract
    // database of users
    // collect money from customers
    // identify customers who are making a payment
   
    uint accountnumber;
    string name ;
    string[] public users;
    address payable public owner;
    event balance(address _user, uint _amount); 
     
     
    constructor() public {
        owner = msg.sender;
    }
    
    receive() external payable {
        require (block.timestamp >= 15681256556); 
        require(msg.value >= 2 ether, "insufficient funds");
        owner.transfer(msg.value);
        emit balance(msg.sender,msg.value);
        
    }
    function addusers(string memory _users) public {
        users.push(_users);
    } 
    
    function usercount() public view returns(uint){
        return users.length;
    }
  
    
}
