# tmux-exercism

Bash scripts to download exercises from [exercism.io](https://exercism.io) and start tmux session with neovim, continuously running the tests when files change.

## requirements

- exercism cli - to download the exercises - <https://exercism.org/docs/using/solving-exercises/working-locally>

- [byobu](https://www.byobu.org/) - tmux wrapper, can be replaced with vanilla [tmux](https://tmux.github.io/)

- [neovim](https://neovim.io/) - preferably with LSP servers for the respective languages

- tools to build and run the tests (specifics per track)
  - **bash**: bats
  - **jq**: bats
  - **lua**: lua, busted
  - **powershell**: pwsh
  - **python**: pytest

## usage

Run the respective track shell script, with the exercise slug as argument.

```bash
./exercism-<track> <exercise_slug>
```

Example for lua track, resistor-color-duo exercise: 
<https://exercism.org/tracks/lua/exercises/resistor-color-duo>

```bash
./exercism-lua resistor-color-duo
```

After solving the exercise, the solution can be submitted using neovim shell integration.

With the solution file selected, run the following command in neovim:

```
:!exercism submit %
```

## demo

[![asciicast](https://asciinema.org/a/675527.svg)](https://asciinema.org/a/675527)
