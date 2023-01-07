---
sidebar_position: 2
---

# Contract functions

The interface for the RaveV2 contract is as follows:

<details>
  <summary>Solidity Interface</summary>



    function approve(address to, uint256 tokenId) external;

    function balanceOf(address owner) external view returns (uint256);

    function bulkRegister(string[] memory names) external payable;

    function bulkRegisterAndSend(
        string[] memory names,
        address[] memory addresses
    ) external payable;

    function extension() external view returns (string memory);

    function f(uint256 p) external;

    function getAddresses(string memory name)
        external
        view
        returns (string memory);

    function getApproved(uint256 tokenId) external view returns (address);

    function getAvatar(string memory name)
        external
        view
        returns (string memory);

    function getName(address owner, uint256 index)
        external
        view
        returns (string memory);

    function getNames(address owner) external view returns (string[] memory);

    function getOwner(string memory name) external view returns (address);

    function isApprovedForAll(address owner, address operator)
        external
        view
        returns (bool);
    function name() external view returns (string memory);

    function owned(string memory name) external view returns (bool);

    function owner() external view returns (address);

    function ownerOf(uint256 tokenId) external view returns (address);

    function price() external view returns (uint256);

    function registerName(string memory _name) external payable;

    function registerNameAndSend(string memory _name, address sendTo)
        external
        payable;

    function renounceOwnership() external;

    function safeTransferFrom(
        address from,
        address to,
        uint256 tokenId
    ) external;

    function safeTransferFrom(
        address from,
        address to,
        string memory name
    ) external;

    function safeTransferFrom(
        address from,
        address to,
        uint256 tokenId,
        bytes memory data
    ) external;

    function setAddresses(string memory _name, string memory addresses)
        external;

    function setApprovalForAll(address operator, bool approved) external;

    function setAvatar(string memory _name, string memory avatar) external;

    function setURI(address newUri) external;

    function supportsInterface(bytes4 interfaceId) external view returns (bool);

    function symbol() external view returns (string memory);

    function tokenByIndex(uint256 index) external view returns (uint256);

    function tokenOfOwnerByIndex(address owner, uint256 index)
        external
        view
        returns (uint256);

    function tokenURI(uint256 tokenId) external view returns (string memory);

    function totalSupply() external view returns (uint256);

    function transferFrom(
        address from,
        address to,
        uint256 tokenId
    ) external;

    function transferFrom(
        address from,
        address to,
        string memory name
    ) external;

    function transferOwnership(address newOwner) external;

    function treasury() external view returns (address);

    function uri() external view returns (address);


</details>

#### Here is what each function does (exluding [ERC721 functions](https://docs.openzeppelin.com/contracts/2.x/api/token/erc721)):
| Function | Description |
|----------|-------------|
| `function registerName(string memory _name) external payable;`         | Register `_name`.ftm for a price of 5 FTM  |
| `function registerNameAndSend(string memory _name, address sendTo) external payable;` | Register `_name`.ftm for a price of 5 FTM and send it to `sendTo` |
| `function bulkRegister(string[] memory names) external payable;` | Bulk register `names` for a price of 5 FTM each |
| `function bulkRegisterAndSend(string[] memory names, address[] memory addresses) external payable;` | Register `names` and send the names to `addresses` |
| `function getAddresses(string memory name) external view returns (string memory);` | Get the multichain addresses for `name` |
| `function getAvatar(string memory name) external view returns (string memory);`| Get the avatar for `name` |
| `function extension() external view returns (string memory);` | Get the registrar's extension (e.g. ftm) |
| `function getName(address owner, uint256 index) external view returns (string memory);` | Get the name owned by `owner` at index `index` by ERC721Enumerable specifications |
| `function getNames(address owner) external view returns (string[] memory);`| ⚠ This function is known to be very slow, do not use in production builds! ⚠ <br /> Get all names owned by an address. |
| `function getOwner(string memory name) external view returns (address);` | Gets the owner of `name` |
| `function safeTransferFrom(address from, address to, string memory name) external;` | Transfer `name` from `from` to `to` |
| `function setAddresses(string memory _name, string memory addresses) external;` | Set the multichain addresses for `_name` as `addresses` |
| `function setAvatar(string memory _name, string memory avatar) external;` | Set the avatar for `_name` as `avatar` |
| `function transferFrom(address from, address to, string memory name) external;` | Equivalent of `safeTransferFrom(address,address,string)` for `transferFrom` |
| `function treasury() external view returns (address);` | The treasury address |
| `function uri() external view returns (address);` | The `tokenURI` generator address |