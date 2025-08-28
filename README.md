# Appcontextjsx
import React, { createContext, useState } from 'react';

const AppContext = createContext();

const AppProvider = ({ children }) => {
  const [usuario, setUsuario] = useState({ nome: 'João', idade: 30 });
  const [tema, setTema] = useState('claro');

  const toggleTema = () => {
    setTema(tema === 'claro' ? 'escuro' : 'claro');
  };

  return (
    <AppContext.Provider value={{ usuario, setUsuario, tema, toggleTema }}>
      {children}
    </AppContext.Provider>
  );
};

export { AppContext, AppProvider };
