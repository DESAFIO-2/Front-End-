# SUS Digital — App (Front-End)

App mobile do SUS Digital feito com **Expo (React Native) + NativeWind (Tailwind)**.

## Como rodar

Requisitos: **Node 22.13+** (o React Native 0.88 pede Node 22 ou superior) e o app **Expo Go** no celular.

```bash
npm install
npx expo start
```

Escaneie o QR code com o Expo Go (Android) ou com a câmera (iPhone).

Login de demonstração: qualquer CPF com 11 dígitos e senha com 4+ caracteres.

## Telas

| Rota | Tela |
| --- | --- |
| `(auth)/login` | Login com CPF e senha |
| `(auth)/cadastro` | Cadastro em 3 passos |
| `(tabs)/inicio` | Início — CNS, remédios do dia, agenda |
| `(tabs)/farmacias` | Farmácias credenciadas perto de você |
| `(tabs)/remedios` | Remédios e alarmes |
| `(tabs)/receitas` | Receitas digitais com código para a farmácia |
| `(tabs)/zelo` | Chat com a assistente Zelo |
| `notificacoes` | Central de notificações |
| `perfil` | Dados do usuário e preferências |
| `alerta-pulseira` | Prévia e teste do alerta mini na pulseira/relógio |

## Alerta na pulseira inteligente

Os alarmes de dose são notificações locais (`expo-notifications`) com texto curto, vibração forte e
botões **Tomei** / **Adiar 15 min**. Pulseiras e relógios pareados ao celular (Mi Band, Amazfit,
Galaxy Fit/Watch, Wear OS, Apple Watch) espelham essas notificações automaticamente, e o toque em
"Tomei" no pulso registra a dose no app.

## Estrutura

```
src/
  app/            rotas (expo-router)
  components/
    layout/       cabeçalho, barra de abas, esqueleto de tela
    ui/           Txt, Icon, Button, Pill, Card, TextField...
  data/mock.ts    dados de exemplo (até ter backend)
  state/          estado global (login, doses, toast)
  theme/          tokens de cor/tipografia e sombras
  utils/          mapas e alarmes
referencias/      HTMLs originais do design
```

## Comandos úteis

```bash
npx tsc --noEmit   # checagem de tipos
npx eslint src     # lint
```
