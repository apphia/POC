# POC
Simple Aadhar Blockchain POC using Python

This is a web flask server run locally.
The POSTMAN REST Client is configured to send the following request

1.POST
http://127.0.0.1:8000/new_transaction

{ "name":"xyz ",
   "address":"Chennai",
   "Aadhar_ID":12345679
}

Content-Type application/json

2.POST
http://127.0.0.1:8000/traffic_transaction

{ 
     "Aadhar_ID": 12345679,
     "violated_count" : 5,
     "severity" : "Critical"
 }


3.GET http://127.0.0.1:8000/mine
Block #1 is mined.

4.POST
  http://127.0.0.1:8000/new_transaction
 { "name":"test user",
   "address":"Tirunelvel",
   "Aadhar_ID":12345
  }

5.POST
 http://127.0.0.1:8000/traffic_transaction
 { 
     "Aadhar_ID": 12345,
     "violated_count" : 15,
     "severity" : "Critical"
 }

6.http://127.0.0.1:8000/chain
{
    "length": 3,
    "chain": [
        {
            "index": 0,
            "transactions": [],
            "timestamp": 0,
            "previous_hash": "0",
            "nonce": 0,
            "hash": "6dbf23122cb5046cc5c0c1b245c75f8e43c59ca8ffeac292715e5078e631d0c9"
        },
        {
            "index": 1,
            "transactions": [
                {
                    "name": "test user",
                    "address": "Tirunelvel",
                    "Aadhar_ID": 12345,
                    "timestamp": 1698920910.9219046
                },
                {
                    "Aadhar_ID": 12345,
                    "violated_count": 5,
                    "severity": "Critical"
                }
            ],
            "timestamp": 1698920937.709309,
            "previous_hash": "6dbf23122cb5046cc5c0c1b245c75f8e43c59ca8ffeac292715e5078e631d0c9",
            "nonce": 36,
            "hash": "006d9bc51ababc13f8fa2b5551d7e8027f41e9726e973e967141aa3dc60e4c17"
        },
        {
            "index": 2,
            "transactions": [
                {
                    "name": "xyz ",
                    "address": "Chennai",
                    "Aadhar_ID": 12345679,
                    "timestamp": 1698920953.5867715
                },
                {
                    "Aadhar_ID": 12345679,
                    "violated_count": 8,
                    "severity": "Critical"
                }
            ],
            "timestamp": 1698920973.0790389,
            "previous_hash": "006d9bc51ababc13f8fa2b5551d7e8027f41e9726e973e967141aa3dc60e4c17",
            "nonce": 610,
            "hash": "003010a8aa3e65163ec1ae199e67e6834f6a6d883f6bac074cee4434c698434c"
        }
    ],
    "peers": []
}
