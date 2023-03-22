# Ophir-NFT

This is a Solidity smart contract for a non-fungible token (NFT) called OphirNFT. It inherits from OpenZeppelin's ERC721, ERC721Enumerable, and ERC721URIStorage contracts. The contract uses the Counters library from OpenZeppelin to keep track of token IDs.


1. The contract has the following state variables:

``_tokenIdCounter``: A counter to track the current token ID.
``MAX_SUPPLY``: The maximum number of tokens that can be minted (10,000).

2. The constructor initializes the base ERC721 contract with the name "OphirNFT" and the symbol "ONT".

3. The ``safeMint`` function allows the contract caller to mint a new NFT with a specified URI. This function ensures that the total supply does not exceed the ``MAX_SUPPLY``. It increments the token ID counter, mints a new token, and sets its URI.

4. 
The contract also includes several overridden functions required by the Solidity compiler:

``_beforeTokenTransfer``: Called before a token transfer or minting operation, ensuring that both ERC721 and ERC721Enumerable hooks are called.

``_burn``: Burns a token by calling both ERC721 and ERC721URIStorage's burn functions.

``tokenURI``: Returns the token URI for a specific token ID, ensuring compatibility with both ERC721 and ERC721URIStorage.

``supportsInterface``: Indicates whether the contract supports a given interface ID, ensuring compatibility with both ERC721 and ERC721Enumerable.
