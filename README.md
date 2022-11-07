
# Biblioteca para logar a entrada e saída de métodos no Java


## Formas de utilização da biblioteca

Para utilizar a biblioteca basta adicionar a anotação @LogEntryExit no método que queira logar

```bash
@RestController
public class ClienteController {

	@LogEntryExit(value = LogLevel.INFO, unit = ChronoUnit.SECONDS, showArgs = true, showResult = false, showExecutionTime = true)
	public ResponseEntity<Void> salvar(@RequestBody ClienteDTO body) {
		// ...
	}
	
	@LogEntryExit(value = LogLevel.INFO, unit = ChronoUnit.SECONDS, showArgs = true, showResult = true, showExecutionTime = true)
	public ResponseEntity<ClienteDTO> consultar(@PathVariable Long id) {
		// ...
	}
}
```

```bash
@Service
public class ClienteService {

	@LogEntryExit(value = LogLevel.DEBUG, unit = ChronoUnit.SECONDS, showArgs = true, showResult = false, showExecutionTime = true)
	public void salvar(ClienteDTO dto) {
		// ...
	}

	@LogEntryExit(value = LogLevel.DEBUG, unit = ChronoUnit.SECONDS, showArgs = true, showResult = true, showExecutionTime = true)
	public ClienteDTO consultar(Long id) {
		// ...
	}
}
```


## Valores padrões da anotação

```bash
  value = LogLevel.INFO
  unit = ChronoUnit.SECONDS
  showArgs = false
  showResult = false
  showExecutionTime = true
```
    
## Variáveis de Ambiente

Biblioteca feita com:

`Spring Boot 2.7.5`

`Java 11`

`Aspectj 1.9.7 `

