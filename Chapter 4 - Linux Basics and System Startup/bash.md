Shell - program that interprets your commands
bash - one specific shell (Bourne Again SHell)
User → [[Virtual Terminal]] → [[Shell]] (bash) → [[Kernel]] → Hardware
 
```bash
# Check your default shell:
echo $SHELL
```
## [[CLI commands]] vs bash:

- Basic commands (ls, cd, cat) work in any shell
- Bash-specific features (syntax, scripting) only work in bash

```bash
# This works in any shell
ls -la

# This is bash-specific syntax
if [[ $var == "test" ]]; then echo "yes"; fi
```
