<template>
    <main id="app">
        <nav class="fixed z-5 flex flex-column justify-between items-center w3 vh-100 pv4 bg-black-40">
            <a class="link white hover-light-purple dib w1" href="/">
                <svg id="logo" fill="currentColor" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 234 270.2"><path d="M40.6 44.1L0 67.5v135.1l117 67.6 117-67.6v-46.9zM234 113V67.5L117 0 77.6 22.7z"/></svg>
            </a>
            <footer class="flex flex-column items-center bg-black-40">
                <a class="link white hover-light-purple dib h1 w1 mb3" href="https://github.com/stormwarning" title="GitHub">
                    <svg fill="currentColor" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.414"><path d="M8 0C3.58 0 0 3.582 0 8c0 3.535 2.292 6.533 5.47 7.59.4.075.547-.172.547-.385 0-.19-.007-.693-.01-1.36-2.226.483-2.695-1.073-2.695-1.073-.364-.924-.89-1.17-.89-1.17-.725-.496.056-.486.056-.486.803.056 1.225.824 1.225.824.714 1.223 1.873.87 2.33.665.072-.517.278-.87.507-1.07-1.777-.2-3.644-.888-3.644-3.953 0-.873.31-1.587.823-2.147-.083-.202-.358-1.015.077-2.117 0 0 .672-.215 2.2.82.638-.178 1.323-.266 2.003-.27.68.004 1.364.092 2.003.27 1.527-1.035 2.198-.82 2.198-.82.437 1.102.163 1.915.08 2.117.513.56.823 1.274.823 2.147 0 3.073-1.87 3.75-3.653 3.947.287.246.543.735.543 1.48 0 1.07-.01 1.933-.01 2.195 0 .215.144.463.55.385C13.71 14.53 16 11.534 16 8c0-4.418-3.582-8-8-8"/></svg>
                </a>
                <a class="link white hover-light-purple dib h1 w1 mb5" href="https://twitter.com/stormwarning" title="Twitter">
                    <svg fill="currentColor" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill-rule="evenodd" clip-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.414"><path d="M16 3.038c-.59.26-1.22.437-1.885.517.677-.407 1.198-1.05 1.443-1.816-.634.375-1.337.648-2.085.795-.598-.638-1.45-1.036-2.396-1.036-1.812 0-3.282 1.468-3.282 3.28 0 .258.03.51.085.75C5.152 5.39 2.733 4.084 1.114 2.1.83 2.583.67 3.147.67 3.75c0 1.14.58 2.143 1.46 2.732-.538-.017-1.045-.165-1.487-.41v.04c0 1.59 1.13 2.918 2.633 3.22-.276.074-.566.114-.865.114-.21 0-.416-.02-.617-.058.418 1.304 1.63 2.253 3.067 2.28-1.124.88-2.54 1.404-4.077 1.404-.265 0-.526-.015-.783-.045 1.453.93 3.178 1.474 5.032 1.474 6.038 0 9.34-5 9.34-9.338 0-.143-.004-.284-.01-.425.64-.463 1.198-1.04 1.638-1.7z" fill-rule="nonzero"/></svg>
                </a>
            </footer>
        </nav>
        <router-view></router-view>
    </main>
</template>

<style>
:root {
    --bg: #16191b;
    --fg: #e2e6e8;
}

body {
    color: var(--fg);
    background-color: var(--bg);
}

#app {
    /*display: grid;
    grid-template-columns: 64px 1fr;
    grid-template-areas: "nav article";*/
    min-height: 100vh;
}

nav {
    grid-area: nav;
}

article {
    @media (min-width: 480px) {
        display: grid;
        grid-template-columns: 1fr 1fr;
        /*grid-template-rows: 1fr 1fr;*/
        grid-template-areas: "header main";
        grid-area: article;
        /*grid-column-start: n-start;*/
    }

    > header {
        background-color: var(--bg);
        background-blend-mode: lighten;

        @media (min-width: 480px) {
            grid-column: header;
            grid-row-start: header-start;
            grid-row-end: controls-end;
        }

        > figure {
            background-color: var(--bg);
            mix-blend-mode: lighten;
            background-blend-mode: luminosity;
        }

        /*> div { left: 8rem; }*/
    }

    /*> aside {
        grid-area: controls;
    }*/

    > main {
        @media (min-width: 480px) {
            grid-area: main;
        }

        > p {
            line-height: 2;
        }

        > :last-child { margin-bottom: 0; }
    }
}

footer {
    /*display: none;*/
    /*flex-direction: column;*/
    /*justify-content: flex-end;*/
    /*grid-area: f;*/
    /*width: 100%;*/
}

abbr[title] {
    text-decoration: none;
}

/*.c2sc {
    text-transform: uppercase;
    font-variant-caps: all-small-caps;
    -ms-font-feature-settings: "smcp" 0, "c2sc";
}

@supports (font-variant-caps: all-small-caps) or (font-feature-settings: "c2sc") {
  .c2sc {
    text-transform: lowercase;
  }
}

@supports not (font-variant-caps: all-small-caps) {
  .c2sc {
    -webkit-font-feature-settings: "onum", "smcp" 0, "c2sc", "smcp", "c2sc";
    font-feature-settings: "onum", "smcp" 0, "c2sc", "smcp", "c2sc";
  }
}*/
</style>
