Implementation Structure 

federated_encryption/
├── keys/
│   ├── client_keys.pkl
│   ├── server_keys.pkl
├── encryption/
│   ├── keygen.py
│   ├── encrypt_client.py
│   ├── decrypt_client.py
│   ├── encrypt_server.py
│   ├── decrypt_server.py
├── quantum/
│   ├── teleportation.py
├── main_federated_loop.py use this and implement two way 

| Process                 | Direction        | Key Used           | Function                     |
|-------------------------|------------------|--------------------|------------------------------|
| Global Model Encryption | Server → Clients | Client public key  | encrypt_global_model()       |
| Global Model Decryption | Client           | Client private key | decrypt_global_model()       |
| Local Model Encryption  | Client → Server  | Server public key  | encrypt_model_bytes()        |
| Local Model Decryption  | Server           | Server private key | decrypt_and_assign_weights() |
