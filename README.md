import { useState } from 'react';
import { Button } from "/components/ui/button";

export default function Home() {
  const [num1, setNum1] = useState(0);
  const [num2, setNum2] = useState(0);
  const [result, setResult] = useState(0);
  const [operator, setOperator] = useState('+');

  const calculate = () => {
    if (operator === '+') {
      setResult(num1 + num2);
    } else if (operator === '-') {
      setResult(num1 - num2);
    } else if (operator === '*') {
      setResult(num1 * num2);
    } else if (operator === '/') {
      setResult(num1 / num2);
    }
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen bg-blue-100">
      <h1 className="text-5xl font-bold mb-4">BotherZigaBot</h1>
      <p className="text-2xl text-center mb-8">Универсальный бот, в котором можно найти все ответы. Бот обновляется каждый день. Лучший бот для готовых ответов и т.п. — BotherZigaBot.</p>
      <div className="bg-white p-8 rounded-lg shadow-lg mb-8">
        <h2 className="text-3xl font-bold mb-4">Протестируйте наш калькулятор!</h2>
        <div className="flex flex-row mb-4">
          <input type="number" value={num1} onChange={(e) => setNum1(Number(e.target.value))} className="w-1/2 p-2 border border-gray-300 rounded-lg" />
          <select value={operator} onChange={(e) => setOperator(e.target.value)} className="w-1/4 p-2 border border-gray-300 rounded-lg">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
          </select>
          <input type="number" value={num2} onChange={(e) => setNum2(Number(e.target.value))} className="w-1/2 p-2 border border-gray-300 rounded-lg" />
        </div>
        <Button onClick={calculate}>Рассчитать</Button>
        <p className="text-2xl font-bold mt-4">Результат: {result}</p>
      </div>
      <a href="https://t.me/botherzigabot" target="_blank" rel="noopener noreferrer">
        <Button variant="secondary">Подробнее</Button>
      </a>
      <div className="flex flex-row justify-center mt-8">
        <a href="https://github.com/your-repo" target="_blank" rel="noopener noreferrer">
          <img src="https://github.githubassets.com/images/modules/logos_page/Octocat.png" alt="GitHub" className="w-8 h-8 mr-4" />
        </a>
        <a href="https://github.com/your-repo" target="_blank" rel="noopener noreferrer" className="text-2xl font-bold">GitHub</a>
      </div>
    </div>
  );
}
