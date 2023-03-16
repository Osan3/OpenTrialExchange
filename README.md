# Open Trial Exchange

Open Trial Exchange is an open source project for securely exchanging confidential information and intellectual property in the clinical trial process. It leverages the security and encryption capabilities of OpenSSL, GnuPG, Keybase, and IPFS to provide a secure and compliant environment for exchanging sensitive information.

## Key Features
- End-to-end encryption using OpenSSL and GnuPG
- Secure key management using Keybase
- Distributed file storage using IPFS, allowing data and intellectual property providers to seed their data on the network
- Authorized access control, ensuring that only authorized users can access the encrypted data
- Compliance with industry standards and regulations


## API

### Seed

```
POST /api/v1/seed

Request Body:
{
	"data": <base64 encoded encrypted data>,
	"encryption_key": <hex encoded encryption key>
}

Response:
{
	"hash": <ipfs hash of the seeded data>
}

GET /api/v1/data/{hash}

Request Body:
{
	"encryption_key": <hex encoded encryption key>
}

Response:
{
	"data": <base64 encoded encrypted data>,
	"status": "available"
}

GET /api/v1/status/{hash}

Response:
{
	"status": "available" | "unavailable"
}

```

The /api/v1/seed endpoint allows data and intellectual property providers to seed their encrypted data on IPFS by sending a POST request with the encrypted data and encryption key in the request body. The response will include the IPFS hash of the seeded data.

The /api/v1/data/{hash} endpoint allows authorized users to retrieve the encrypted data from IPFS by sending a GET request with the encryption key in the request body. The response will include the encrypted data.

GET /api/v1/status/{hash} endpoint allows clients to check the availability of the seeded data on IPFS. The response will include a status field that indicates whether the data is available ("available") or unavailable ("unavailable").

## Getting Started

To get started with Open Trial Exchange, you will need to install the following components:

- OpenSSL
- GnuPG
- Keybase
- IPFS
Once you have installed the required components, you can configure Open Trial Exchange to meet your specific security and compliance requirements. Data and intellectual property providers can then seed their data on IPFS, encrypting it and making it only accessible by authorized users.

## Contributing
Open Trial Exchange is an open source project and we welcome contributions from the community. If you would like to contribute, please see our Contribution Guidelines for more information.

## License
Open Trial Exchange is released under the MIT License.