# toOuches
## creating an instance of the \<DEX \/\> component in React

### `DEX api`

### `useOneInchQuote()`

💸 api for getting swap quote info.

**Example**:


import { useOneInchQuote } from "react-moralis";

function Quote() {
  const { getQuote, data, isFetching, isLoading, error } = useOneInchQuote({
    chain: "bsc", // The blockchain you want to use (eth/bsc/polygon)
    fromTokenAddress: "0x0da6ed8b13214ff28e9ca979dd37439e8a88f6c4", // The token you want to swap
    toTokenAddress: "0x6fd7c98458a943f469e1cf4ea85b173f5cd342f4", // The token you want to receive
    amount: 1000,
  });
  return (
    <div>
      {error && <>{JSON.stringify(error)}</>}
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}


### `useOneInchQuote()`

💸 api for swap.

**Example**:


import { useOneInchQuote } from "react-moralis";

function Swap() {
  const { swap, data, isFetching, isLoading, error } = useOneInchSwap();

  const options = {
    chain: "bsc", // The blockchain you want to use (eth/bsc/polygon)
    fromTokenAddress: "0x0da6ed8b13214ff28e9ca979dd37439e8a88f6c4", // The token you want to swap
    toTokenAddress: "0x6fd7c98458a943f469e1cf4ea85b173f5cd342f4", // The token you want to receive
    amount: 1000,
    fromAddress: "0x6217e65d864d77DEcbFF0CFeFA13A93f7C1dD064", // Your wallet address
    slippage: 1,
  };

  return (
    <div>
      {error && <>{JSON.stringify(error)}</>}
      <button onClick={() => swap(options)}>Swap</button>
    </div>
  );
}
