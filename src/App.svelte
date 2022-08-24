<script lang="ts">
    let name = "OffeeX";
    const logos = [
        {name: "github", link: "https://github.com/OffeeX", color: "#3b4659"},
        {name: "youtube", link: "https://www.youtube.com/channel/UCUOBXFx8lsQdMVRvtgSAeVg", color: "#493333"},
        {name: "discord", link: "https://discord.gg/aR9mB6S4", color: "#393e65"}
    ]

    function randomNumber(min, max) {
        return Math.round((Math.random() * Math.abs(max - min)) + min);
    }

    function timeOut() {
        setTimeout(() => {
            switch (randomNumber(0, 3)) {
                case 0: {
                    name = "OffeeX";
                    break
                }
                case 1: {
                    name = "Offeex";
                    break
                }
                case 2: {
                    name = "offeeX";
                    break
                }
                case 3: {
                    name = "offeex";
                    break
                }
            }
            timeOut()
        }, randomNumber(100, 800))
    }

    timeOut()
</script>

<body>
<header>
</header>

<main>
    <div class="center">
        <div class="container">
            <p title="{name}" class="glitch">{name}</p>
        </div>
        <div class="logos">
            {#each logos as logo}
                <a target="_blank" href="{logo.link}"><img class="logo" src="/logos/{logo.name}.png" alt="" style="--accent-color: {logo.color}"></a>
            {/each}
        </div>
    </div>
</main>

<footer>
</footer>
</body>

<style lang="scss">
  @import "styles/centerText.scss";

  .center {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 200px;
  }

  .logos {
    display: flex;
    gap: 10px;
    justify-content: center;
  }

  .logo {
    --accent-color: #6b5f9a;

    height: 48px;
    border-radius: 10px 10px 10px 10px;

    box-sizing: border-box;
    padding: 3px;

    border-width: 2px 2px 1px 2px;
    border-style: solid;
    border-color: var(--accent-color);

    transition: border-color 0.2s, scale 0.4s;

    &:hover {
      border-color: transparent;
      scale: 1.3;
    }
  }
</style>