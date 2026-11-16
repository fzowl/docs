# Voyage AI by MongoDB

On Epsilla Cloud, you can enable the Voyage AI by MongoDB integration by providing your Voyage AI by MongoDB API key (we securely manage your keys using AWS KMS):

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-18 at 8.52.45 AM.png" alt=""><figcaption></figcaption></figure>

## Embeddings

Epsilla integrates with Voyage AI by MongoDB with the following embedding models:

| Name                                 | Dimensions |
|--------------------------------------|------------|
| **voyageai/voyage-4-large**          | 1024       |
| **voyageai/voyage-4**                | 1024       |
| **voyageai/voyage-4-lite**           | 1024       |
| **voyageai/voyage-code-4**           | 1024       |
| **voyageai/voyage-context-4**        | 1024       |
| **voyageai/voyage-multimodal-3.5**   | 1024       |
| **voyageai/voyage-multimodal-3**     | 1024       |
| **voyageai/voyage-context-3**        | 1024       |
| **voyageai/voyage-3.5**              | 1024       |
| **voyageai/voyage-3.5-lite**         | 1024       |
| **voyageai/voyage-3-large**          | 1024       |
| **voyageai/voyage-3**                | 1024       |
| **voyageai/voyage-3-lite**           | 512        |
| **voyageai/voyage-code-3**           | 1024       |
| **voyageai/voyage-large-2-instruct** | 1024       |
| **voyageai/voyage-finance-2**        | 1024       |
| **voyageai/voyage-multilingual-2**   | 1024       |
| **voyageai/voyage-law-2**            | 1024       |
| **voyageai/voyage-code-2**           | 1536       |
| **voyageai/voyage-large-2**          | 1536       |
| **voyageai/voyage-2**                | 1024       |

For Epsilla open source vector db, you just need to add a header in the data ingestion and semantic search queries [like this](../../vector-database/embeddings.md#voyage-ai-by-mongodb-embedding).

Then you can start using the Voyage AI by MongoDB embedding models during vector table schema creation:

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 12.10.07 PM.png" alt=""><figcaption></figcaption></figure>
