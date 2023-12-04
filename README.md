bash
npx create-react-app react-list-app
cd react-list-app

jsx

import React, { useState } from 'react';
import './App.css';
import ListItem from './ListItem';

function App() {
  const [items, setItems] = useState([]);
  const [inputText, setInputText] = useState('');

  const addItem = () => {
    if (inputText.trim() !== '') {
      setItems([...items, inputText]);
      setInputText('');
    }
  };

  return (
    <div className="app">
      <h1>Lista de Itens</h1>
      <div className="form">
        <input
          type="text"
          value={inputText}
          onChange={(e) => setInputText(e.target.value)}
        />
        <button onClick={addItem}>Adicionar</button>
      </div>
      <ul>
        {items.map((item, index) => (
          <ListItem key={index} text={item} />
        ))}
      </ul>
    </div>
  );
}

export default App;

jsx

import React from 'react';
import './ListItem.css';

function ListItem({ text }) {
  return <li className="list-item">{text}</li>;
}

export default ListItem;

css

.app {
  text-align: center;
  padding: 20px;
}

.form {
  margin-bottom: 20px;
}

input {
  margin-right: 10px;
}

ul {
  list-style-type: none;
  padding: 0;
}

bash

npm run build
git init
git add .
git commit -m "Initial commit"
git remote add origin SEU_REPO_DO_GITHUB
git push -u origin master
