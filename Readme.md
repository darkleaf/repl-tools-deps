Обертка над [bhauman/rebel-readline](https://github.com/bhauman/rebel-readline).

Добавляет поддержку [reloading](https://github.com/clojure/tools.namespace/) с помощью команд

+ `:repl/reload`
+ `:repl/reload-all`

```edn
{:aliases
 {:repl {:extra-deps {darkleaf/repl-tools-deps
                      {:git/url "https://github.com/darkleaf/repl-tools-deps.git"
                       :sha     "" }}
         :main-opts ["-m" "darkleaf.repl-tools-deps"]}}
}
```

или

```edn
{:aliases
 {:repl {:extra-deps {darkleaf/repl-tools-deps
                      {:git/url "https://github.com/darkleaf/repl-tools-deps.git"
                       :sha     "" }}
         :main-opts ["-m" "darkleaf.repl-tools-deps"
                     "reload-before-fn" "user/stop"
                     "reload-after-fn" "user/start"]}}
}
```

Если при перезагрузке произошла ошибка, то она доступна как `*e`:

```
:repl/reload-all
:reloading (some.namespace)
:error-while-loading some.namespace
user=> *e
#error {
...
}
```

Добавляет поддержку запуска тестов с помощью команд:

+ `:repl/run-tests`
