## Terminal and Application Icons with Nerd-Fonts

To display icons in terminal or applications Fonts, I'm using [Nerd-Fonts](https://www.nerdfonts.com). I'm currently using the **FiraCode Nerd Font**

## Configuration

I'm currently using [Starship](https://starship.rs/), to install it you need:

- A [Nerd Font](https://www.nerdfonts.com) installed and enabled in your terminal.

- Get the starship binary onto your computer.

- Tell your shell to use the starship binary as its prompt by modifying its init scripts.

### Linux

- Install the starship binary: `curl -sS https://starship.rs/install.sh | sh`

- Create the folder and copy starship.toml: `mkdir -p ~/.config && vim ~/.config/starship.toml`

- Add the following to the end of ~/.bashrc: `vim ~/.bashrc`

```bash
# ~/.bashrc
...

eval "$(starship init bash)"
```

- Finally reload your bash config: `source ~/.bashrc`

### Powershell

- Install the starship binary: `winget install starship or scoop install starship`

- Modify Execution Policy for scripts: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

- Check you set correctly the policy: `Get-ExecutionPolicy -List`

- Create the folder and copy starship.toml: `mkdir -p ~/.config && vim ~/.config/starship.toml`

- Add the following to the end of Microsoft.PowerShell_profile.ps1: `code $PROFILE`

```Powershell
# ~\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
...

Invoke-Expression (&starship init powershell)
```

- Finally reload your terminal.

### Git bash

- Make/Choose folder where to install: `mkdir -p ~/bin/starship && cd ~/bin`

- Download the install script: `curl -fsSL https://starship.rs/install.sh > ./install.sh`

- Run install script: `./install.sh --bin-dir /c/Users/<USERNAME>/bin/starship/ --platform pc-windows-msvc`

- Create the folder and copy starship.toml: `mkdir -p ~/.config && vim ~/.config/starship.toml` [Optional if you've already configured Powershell]

- Add the following to the end of your .bashrc file: `vim ~/.bashrc`

```bash
# ~/.bashrc
...

export PATH=$PATH:"/c/Users/<USERNAME>/bin/starship"
eval "$(starship init bash)"
```

- Finally reload your bash config: `source ~/.bashrc`
