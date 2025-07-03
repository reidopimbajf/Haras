function verificarLogin() {
  if (!localStorage.getItem("user")) {
    alert("Você precisa estar logado!");
    window.location.href = "login.html";
  }
}

function login() {
  const user = document.getElementById("login-username").value;
  const pass = document.getElementById("login-password").value;
  const usuarios = JSON.parse(localStorage.getItem("usuarios") || "[]");
  const encontrado = usuarios.find(u => u.username === user && u.password === pass);
  if (encontrado) {
    localStorage.setItem("user", JSON.stringify(encontrado));
    window.location.href = "dashboard.html";
  } else {
    alert("Login inválido!");
  }
}

function cadastrar() {
  const username = document.getElementById("cad-username").value;
  const password = document.getElementById("cad-password").value;
  const role = document.getElementById("cad-role").value;
  const usuarios = JSON.parse(localStorage.getItem("usuarios") || "[]");
  if (usuarios.find(u => u.username === username)) {
    alert("Usuário já existe!");
    return;
  }
  usuarios.push({ username, password, role });
  localStorage.setItem("usuarios", JSON.stringify(usuarios));
  alert("Usuário cadastrado com sucesso!");
  window.location.href = "login.html";
}

function logout() {
  localStorage.removeItem("user");
  window.location.href = "login.html";
}

function salvarCavalo() {
  const cavalo = {
    nome: document.getElementById("nome").value,
    raca: document.getElementById("raca").value,
    idade: document.getElementById("idade").value,
    modalidade: document.getElementById("modalidade").value,
    obs: document.getElementById("obs").value
  };
  const cavalos = JSON.parse(localStorage.getItem("cavalos") || "[]");
  cavalos.push(cavalo);
  localStorage.setItem("cavalos", JSON.stringify(cavalos));
  alert("Cavalo cadastrado!");
  listarCavalos();
}

function listarCavalos() {
  const lista = document.getElementById("lista-cavalos");
  const cavalos = JSON.parse(localStorage.getItem("cavalos") || "[]");
  lista.innerHTML = "";
  cavalos.forEach(c => {
    const li = document.createElement("li");
    li.innerText = `${c.nome} - ${c.modalidade}`;
    lista.appendChild(li);
  });
}

function carregarCavalosSelect() {
  const select = document.getElementById("cavalo");
  const cavalos = JSON.parse(localStorage.getItem("cavalos") || "[]");
  select.innerHTML = "";
  cavalos.forEach((c, i) => {
    const opt = document.createElement("option");
    opt.value = i;
    opt.innerText = c.nome;
    select.appendChild(opt);
  });
}

function carregarCavalosSelectTreino() {
  const select = document.getElementById("cavalo-treino");
  const cavalos = JSON.parse(localStorage.getItem("cavalos") || "[]");
  select.innerHTML = "";
  cavalos.forEach((c, i) => {
    const opt = document.createElement("option");
    opt.value = i;
    opt.innerText = c.nome;
    select.appendChild(opt);
  });
}

function registrarAlimentacao() {
  const alimentacoes = JSON.parse(localStorage.getItem("alimentacoes") || "[]");
  alimentacoes.push({
    cavalo: document.getElementById("cavalo").value,
    data: document.getElementById("data").value,
    tipo: document.getElementById("tipo").value,
    quantidade: document.getElementById("quantidade").value
  });
  localStorage.setItem("alimentacoes", JSON.stringify(alimentacoes));
  alert("Alimentação registrada!");
}

function registrarTreino() {
  const treinos = JSON.parse(localStorage.getItem("treinos") || "[]");
  treinos.push({
    cavalo: document.getElementById("cavalo-treino").value,
    modalidade: document.getElementById("modalidade").value,
    data: document.getElementById("data").value,
    duracao: document.getElementById("duracao").value,
    obs: document.getElementById("obs").value
  });
  localStorage.setItem("treinos", JSON.stringify(treinos));
  alert("Treino registrado!");
}

function gerarRelatorio() {
  const cavalos = JSON.parse(localStorage.getItem("cavalos") || "[]");
  const alimentacoes = JSON.parse(localStorage.getItem("alimentacoes") || "[]");
  const treinos = JSON.parse(localStorage.getItem("treinos") || "[]");
  const div = document.getElementById("relatorio-geral");
  div.innerHTML = "";
  cavalos.forEach((c, i) => {
    const cavDiv = document.createElement("div");
    cavDiv.innerHTML = `<h3>${c.nome}</h3>`;
    const alim = alimentacoes.filter(a => a.cavalo == i);
    const trn = treinos.filter(t => t.cavalo == i);
    cavDiv.innerHTML += `<p>Alimentações: ${alim.length}, Treinos: ${trn.length}</p>`;
    div.appendChild(cavDiv);
  });
}
