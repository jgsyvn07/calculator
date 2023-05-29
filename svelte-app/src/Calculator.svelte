<script>
  let displayValue = '';
  
  function handleButtonClick(value) {
    displayValue += value;
  }
  
  function calculate() {
    try {
      displayValue = eval(displayValue);
    } catch (error) {
      displayValue = 'Error';
    }
  }
  
  function clear() {
    displayValue = '';
  }
</script>

<style>
  .calculator {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 10px;
    max-width: 200px;
  }
  
  .display {
    grid-column: span 4;
    height: 40px;
    background-color: #f5f5f5;
    text-align: right;
    padding: 10px;
    font-size: 20px;
  }
  
  button {
    height: 40px;
    background-color: #f5f5f5;
    border: 1px solid #ccc;
    cursor: pointer;
    font-size: 18px;
  }
</style>

<div class="calculator">
  <div class="display">{displayValue}</div>
  <button on:click={() => handleButtonClick('1')}>1</button>
  <button on:click={() => handleButtonClick('2')}>2</button>
  <button on:click={() => handleButtonClick('3')}>3</button>
  <button on:click={() => handleButtonClick('+')}>+</button>
  <button on:click={() => handleButtonClick('4')}>4</button>
  <button on:click={() => handleButtonClick('5')}>5</button>
  <button on:click={() => handleButtonClick('6')}>6</button>
  <button on:click={() => handleButtonClick('-')}>-</button>
  <button on:click={() => handleButtonClick('7')}>7</button>
  <button on:click={() => handleButtonClick('8')}>8</button>
  <button on:click={() => handleButtonClick('9')}>9</button>
  <button on:click={() => handleButtonClick('*')}>*</button>
  <button on:click={() => handleButtonClick('0')}>0</button>
  <button on:click={() => handleButtonClick('.')}>.</button>
  <button on:click={() => calculate()}>=</button>
  <button on:click={() => handleButtonClick('/')}>/</button>
  <button on:click={() => clear()}>C</button>
</div>