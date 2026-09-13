# Setup for Stockfish 19

## 1. Download:
```
!pip install aiohttp
!wget https://github.com/official-stockfish/Stockfish/releases/latest/download/stockfish-linux-x86-64-universal.tar.gz
!wget https://github.com/lichess-org/external-engine/raw/main/example-provider.py
```
## 2. Extract:
```
!tar -xzf stockfish-linux-x86-64-universal.tar.gz
```
## 3. Usage (Help):
```
!python example-provider.py -h
```
### Output:
```
usage: example-provider.py [-h] [--name NAME] --engine ENGINE
                           [--setoption NAME VALUE] [--lichess LICHESS]
                           [--broker BROKER] [--token TOKEN]
                           [--provider-secret PROVIDER_SECRET]
                           [--max-threads MAX_THREADS] [--max-hash MAX_HASH]
                           [--keep-alive KEEP_ALIVE]
                           [--log-level {critical,error,warning,info,debug,notset}]

options:
  -h, --help            show this help message and exit
  --name NAME           Engine name to register
  --engine ENGINE       Shell command to launch UCI engine
  --setoption NAME VALUE
                        Set a custom UCI option
  --lichess LICHESS     Defaults to https://lichess.org
  --broker BROKER       Defaults to https://engine.lichess.ovh
  --token TOKEN         API token with engine:read and engine:write scopes
  --provider-secret PROVIDER_SECRET
                        Optional fixed provider secret
  --max-threads MAX_THREADS
                        Maximum number of available threads
  --max-hash MAX_HASH   Maximum hash table size in MiB
  --keep-alive KEEP_ALIVE
                        Number of seconds to keep an idle/unused engine
                        process around
  --log-level {critical,error,warning,info,debug,notset}
                        Logging verbosity
```
## 4. Run:
```
!LICHESS_API_TOKEN=your-api-token python example-provider.py --engine stockfish/stockfish-linux-x86-64-universal --name "Stockfish 19 (External)"
```
>Replace `your-api-token` with your Lichess API token
