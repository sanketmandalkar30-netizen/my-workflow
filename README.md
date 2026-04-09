{
  "name": "My workflow",
  "nodes": [
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.chatTrigger",
      "typeVersion": 1.4,
      "position": [
        0,
        0
      ],
      "id": "a6b87ff7-4a19-4a97-b81d-9dd5309a0191",
      "name": "When chat message received",
      "webhookId": "458fe5d4-2c17-43b2-9c9e-ff06dfdfb88b"
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.agent",
      "typeVersion": 3.1,
      "position": [
        208,
        0
      ],
      "id": "271d6be7-05d6-4fd2-80f3-6941f65c55be",
      "name": "AI Agent"
    },
    {
      "parameters": {},
      "type": "@n8n/n8n-nodes-langchain.memoryBufferWindow",
      "typeVersion": 1.3,
      "position": [
        224,
        208
      ],
      "id": "b2641a8b-ced9-4d4d-88a0-bd65d7396001",
      "name": "Simple Memory"
    },
    {
      "parameters": {},
      "type": "@n8n/n8n-nodes-langchain.toolCalculator",
      "typeVersion": 1,
      "position": [
        448,
        240
      ],
      "id": "4c4c3de7-cb1f-4a23-8570-6e6ec11ee4ac",
      "name": "Calculator"
    },
    {
      "parameters": {
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.toolSerpApi",
      "typeVersion": 1,
      "position": [
        352,
        256
      ],
      "id": "f1021858-338b-4236-89c9-406f7d6ac3ae",
      "name": "SerpAPI",
      "credentials": {
        "serpApi": {
          "id": "iX6nZBHzAFJoegGN",
          "name": "SerpAPI account"
        }
      }
    },
    {
      "parameters": {
        "model": {
          "__rl": true,
          "mode": "list",
          "value": "gpt-4.1-mini"
        },
        "builtInTools": {},
        "options": {}
      },
      "type": "@n8n/n8n-nodes-langchain.lmChatOpenAi",
      "typeVersion": 1.3,
      "position": [
        80,
        208
      ],
      "id": "20db9ee4-cd31-4c57-b653-e19bfff69725",
      "name": "OpenAI Chat Model",
      "credentials": {
        "openAiApi": {
          "id": "4o0w2rAC69r3lTTN",
          "name": "n8n free OpenAI API credits"
        }
      }
    }
  ],
  "pinData": {},
  "connections": {
    "When chat message received": {
      "main": [
        [
          {
            "node": "AI Agent",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Simple Memory": {
      "ai_memory": [
        [
          {
            "node": "AI Agent",
            "type": "ai_memory",
            "index": 0
          }
        ]
      ]
    },
    "Calculator": {
      "ai_tool": [
        [
          {
            "node": "AI Agent",
            "type": "ai_tool",
            "index": 0
          }
        ]
      ]
    },
    "SerpAPI": {
      "ai_tool": [
        [
          {
            "node": "AI Agent",
            "type": "ai_tool",
            "index": 0
          }
        ]
      ]
    },
    "OpenAI Chat Model": {
      "ai_languageModel": [
        [
          {
            "node": "AI Agent",
            "type": "ai_languageModel",
            "index": 0
          }
        ]
      ]
    }
  },
  "active": true,
  "settings": {
    "executionOrder": "v1",
    "availableInMCP": false
  },
  "versionId": "76c6120e-9d73-4253-8ae7-3f8b8f98cc4a",
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "330096cb938dded25040097c1c917c04ca4526b8b7e0e5c1458734774ae1158d"
  },
  "id": "nIjLEp-A_H96NMKnVYtgf",
  "tags": []
}
