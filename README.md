#  Maratona Rustrimeitor
## Placar para live streaming do BOCA para uso no OBS

Este placar foi feito para as etapas regional e nacional da Maratona de Programação da SBC.

## Compilando e Rodando

Pré-requisitos:

- Instale o [Rust](https://www.rust-lang.org/pt-BR/tools/install)
- Instale o `cargo-make`: 

```
cargo install cargo-make
```

Clone este repositório:

```
git clone https://github.com/wuerges/maratona-animeitor-rust
cd maratona-animeitor-rust
```

Compile e rode:

```
cargo make build_release && cargo run --release -p lib-server <porta_tcp> <url_do_placar>
```

O repositório contém um exemplo, que pode ser usado para testes:

```
python -mhttp.server --directory lib-server/test/
cargo make build_release && cargo run --release -p lib-server 3030 http://0.0.0.0:8000/webcast_1573336220.zip
```


Os parâmetros necessários para rodar são a porta HTTP e a URL disponibilizada pelo BOCA.

## Configurando o OBS e customizando o placar

A partir deste momento, o placar e os runs ficarão disponíveis nas URLs que o programa mostrar:

```
Maratona Rustrimeitor rodando!
-> Placar em http://localhost:3032/static/runPanel.html
-> Runs em http://localhost:3032/static/scoreboard.html
```

Estas urls podem ser acessados no navegador, ou incluídas no OBS, através do browser incluso.

O placar e os runs podem ser customizados usando CSS, através do arquivo [static/styles.css](lib-server/static/styles.css). 

