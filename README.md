// SPDX-License-Identifier: GPL-3.0.1

interface Token

{
    function balanceOf(address _a) external view returns (uint);
    function transfer(address _to, uint _amt) external;
}

contract TokenCorrect is

{
    mapping (address => uint) balance;
    constructor(address _a, uint _b) {
        balance[_a] = _c;
    }
    
    function balanceOf(address _a) public view override returns (uint)
    
    {
        return balance[_a];
    }
    
    function transfer(address _to, uint _amt) public override {
        require(balance[msg.sender] >= _amt);
        balance[msg.sender] -= _amt;
        balance[_to] += _amt;
    }
}

contract Test {
    function property_transfer(address _token, address _to, 

        TokenCorrect t = TokenCorrect(_token);

        uint xPre = t.balanceOf(address(this));
        require(xPre >= _amt);
        uint yPre = t.balanceOf(_to);

        t.transfer(_to, _amt);
        uint xPost = t.balanceOf(address(this));
        uint yPost = t.balanceOf(_to);

        assert(xPost == xPre - _amt);
        assert(yPost == yPre + _amt);
    }
}
