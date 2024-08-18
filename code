How to run a Worker Allora Random 50/50 Prediction Price

Faucet  : https://faucet.testnet-1.testnet.allora.network/

1. Install

Copy
sudo apt-get update
sudo apt-get install -y make gcc jq
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add –
sudo add-apt-repository “deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable”
apt-cache policy docker-ce
sudo apt install docker-ce -y
2. Clone source
Copy
git clone https://github.com/allora-network/allora-huggingface-walkthrough

cd allora-huggingface 
mkdir -p worker-data
chmod -R 777 worker-data

cp config.example.json config.json
3. Edit config.json
Don't forget to add your mnemoric phase inside

Copy
{
    "wallet": {
        "addressKeyName": "test",
        "addressRestoreMnemonic": "<your mnemoric phase>",
        "alloraHomeDir": "/root/.allorad",
        "gas": "1000000",
        "gasAdjustment": 1.0,
        "nodeRpc": "https://allora-rpc.testnet-1.testnet.allora.network/",
        "maxRetries": 1,
        "delay": 1,
        "submitTx": false
    },
    "worker": [
        {
            "topicId": 1,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 5,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "ETH"
            }
        },
        {
            "topicId": 3,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 7,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "BTC"
            }
        },
        {
            "topicId": 5,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 9,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "SOL"
            }
        },
        {
            "topicId": 7,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 5,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "ETH"
            }
        },
        {
            "topicId": 8,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 7,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "BNB"
            }
        },
        {
            "topicId": 9,
            "inferenceEntrypointName": "api-worker-reputer",
            "loopSeconds": 9,
            "parameters": {
                "InferenceEndpoint": "http://inference:8000/inference/{Token}",
                "Token": "ARB"
            }
        }
        
    ]
}
4. Edit init.config
Copy
chmod +x init.config
./init.config
6. Build
Copy
docker compose up --build
Check log 

Copy
docker compose logs -f
Testing Inference Only

Run the following command to start the inference node:

Copy
docker compose up --build inference
Send requests to the inference model. For example, request ETH price inferences:

Copy
curl http://127.0.0.1:8000/inference/ETH
Expected response:

Copy
{"value":"2564.021586281073"}
Update the node's internal state (download pricing data, train, and update the model):

Copy
curl http://127.0.0.1:8000/update
Expected response:

Copy
0
Add Allora chain at keplr wallet . Check uALLO token number if it increases, it shows you have received reward Check Txn number you have completed here : 

http://worker-tx.nodium.xyz/ 
