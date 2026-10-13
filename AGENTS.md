# AGENTS.md

## Worktrees: cada tarea en su propio arbol, nunca en el checkout principal

Cada tarea (feature, bug, chore) se trabaja en un worktree propio, nunca haciendo commits
directamente sobre el checkout principal (el que queda en `master`/`main` tras clonar).

Comando:

```
git worktree add .claude/worktrees/<rama> -b <rama> origin/<rama-principal>
```

**Por que**: puede haber varios agentes trabajando a la vez sobre el mismo repo. Si todos editan
el checkout principal se pisan entre ellos -- un `git status` de otro agente, a medio comando,
puede verse como si fuera el tuyo, o al reves. El checkout principal se queda limpio y en
`master`/`main`, de solo lectura para uso de agentes; cada rama de trabajo vive en su propio
directorio bajo `.claude/worktrees/`.

Antes de la primera edicion de una tarea, comprobar que no se esta en el arbol compartido:

```
git rev-parse --abbrev-ref HEAD   # si dice "master" o "main", PARAR: no es tu worktree
```

## Issues, no PLAN.md

Las features, bugs y sus cambios de plan viven en issues de GitHub, uno por cosa, con los
cambios de alcance como comentarios en su propia issue. Un `PLAN.md`, si existe, es historia --
no se actualiza como plan vivo.

## Nadie abre una issue, nadie la etiqueta

La issue la abre el dueño del producto, y la etiqueta tambien: la etiqueta ES la autorizacion
para trabajarla. Ni un agente ni el manager abren o etiquetan issues por su cuenta. Lo que se
detecte como trabajo pendiente se reporta (con su medida) para que el dueño del producto decida.
