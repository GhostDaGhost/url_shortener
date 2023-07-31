<script lang="ts">
    import logo from '../assets/logo.png';
</script>

<div id="header_outercontainer">
    <div id="logo_container">
        <img
            id="logo"
            src={logo}
            alt="logo"
            draggable="false"
        >
    </div>

    <div id="texts">
        <div id="title_container">
            <h1 id="title">URL Shortener</h1>
        </div>
        
        <div id="author_container">
            <h3 id="author">Created by Alexander Arizola</h3>
        </div>
    </div>
</div>

<style lang="less">
    @import '../styles/HeaderText';
</style>
