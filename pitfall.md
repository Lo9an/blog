1. Must return deepcopy of state when implementing "step" and "reset" method of customized gym env.
2. 
3. Build a git server following RYF's <最简单的git服务器>, then I push a local repository to the server successfully. However, there is nothing but xxx.git. WTF? Found all files are deleted directly when I check `git status`, Nonsense! Finally, I restore them by `git checkout *` manually.
4. 
5. Remeber to take out the comma when use `@dataclasses.dataclass`, e.g. use `val: int = 1`  rather than `val:int = 1,`