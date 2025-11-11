<template>
  <div id="app-wrapper">
    <header class="classic-header">
      <div class="header-content">
        <span class="logo-text">R</span>
        <span class="app-name">Receitas Deliciosas</span>
        <nav class="classic-nav">
          <a href="#" class="nav-item">Início 🏠</a>
          <a href="#" class="nav-item">Receitas 🧑‍🍳</a>
          <a href="#" class="nav-item current"><span class="heart-icon-nav">💖</span> Favoritos</a>
          <a href="#" class="nav-item">Adicionar ➕</a>
        </nav>
      </div>
      <div class="header-controls">
        <span class="search-icon">🔍</span>
        <span class="menu-toggle">≡</span>
      </div>
    </header>

    <main class="favorites-main-content">
      <h1 class="favorites-title-v2">
        <span class="title-heart-icon">💖</span> Minhas Receitas Favoritas
      </h1>

      <p class="saved-count-v2">0 receitas salvas</p>

      <div class="divider"></div>

      <div class="empty-state-v2">
        <p class="empty-message-v2">Nenhuma receita favorita ainda</p>
        <p class="empty-message-v2">Comece a explorar e salvar suas receitas preferidas</p>
        <a href="#" class="explore-link-v2">Explorar Receitas</a>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'FavoritesEmptyV2'
}
</script>

<style scoped>
/* Reset básico para simular um ambiente sem estilos modernos */
#app-wrapper {
  font-family: 'Times New Roman', Times, serif; /* Fonte clássica/padrão do navegador */
  color: #000;
  margin: 0;
  padding: 0;
  background-color: #fff;
}

/* --- Estilos do Cabeçalho e Navegação (Top Bar) --- */

.classic-header {
  /* Remove qualquer estilo de fundo moderno (cores, gradientes) */
  background-color: #fff;
  border-bottom: 1px solid #ccc; /* Linha de separação fraca */
  padding: 8px 15px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
}

.header-content {
  display: flex;
  align-items: center;
}

.logo-text {
  font-size: 18px;
  font-weight: bold;
  color: #333;
  margin-right: 5px;
}

.app-name {
  color: #333;
  font-weight: normal;
  margin-right: 20px;
}

.classic-nav {
  display: flex;
}

.nav-item {
  color: #000;
  text-decoration: none;
  margin-right: 15px;
  padding: 3px 0;
}

.nav-item:hover {
  text-decoration: underline;
}

.nav-item.current {
  color: #d9534f; /* Vermelho/rosa para o item ativo */
  font-weight: bold;
}

.heart-icon-nav {
  margin-right: 3px;
}

.header-controls {
  display: flex;
  gap: 15px;
}

.search-icon, .menu-toggle {
  font-size: 16px;
  cursor: pointer;
  color: #333;
}

/* --- Estilos da Área Principal (Minhas Receitas Favoritas) --- */

.favorites-main-content {
  padding: 20px 40px; /* Mais espaço nas laterais */
  max-width: 900px;
  margin: 0 auto; /* Centraliza o conteúdo principal */
}

.favorites-title-v2 {
  font-size: 24px;
  color: #000;
  margin-top: 15px;
  margin-bottom: 0;
  font-weight: normal; /* Sem negrito forte, como na imagem */
}

.title-heart-icon {
  font-size: 24px;
  margin-right: 5px;
  color: #d9534f; /* Cor do coração */
}

.saved-count-v2 {
  font-size: 14px;
  color: #666;
  margin-top: 5px;
  margin-bottom: 15px;
}

.divider {
  border-bottom: 1px solid transparent; /* Invisível ou apenas um espaço */
  margin-bottom: 10px;
}

/* --- Mensagem de Estado Vazio --- */

.empty-state-v2 {
  margin-top: 5px; /* Espaço para afastar da contagem */
}

.empty-message-v2 {
  font-size: 14px;
  color: #000;
  line-height: 1.4;
  margin-bottom: 3px; /* Menos espaço entre as linhas */
}

.explore-link-v2 {
  font-size: 14px;
  color: #007bff; /* Azul padrão do navegador/link */
  text-decoration: underline;
  cursor: pointer;
  display: block; /* O link fica em sua própria linha */
  margin-top: 8px;
}

.explore-link-v2:hover {
  color: #0056b3;
}
</style>
