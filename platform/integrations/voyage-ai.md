# VoyageAI by MongoDB

> VoyageAI by MongoDB (Voyage AI is now part of MongoDB) provides state-of-the-art embedding and reranking models. Model identifiers keep the `voyageai/` prefix for backward compatibility.

On Epsilla Cloud, you can enable VoyageAI by MongoDB integration by providing your VoyageAI by MongoDB API key (we securely manage your keys using AWS KMS):

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-18 at 8.52.45 AM.png" alt=""><figcaption></figcaption></figure>

## Embeddings

Epsilla integrates with VoyageAI by MongoDB with the following embedding models:

| Name                                 | Dimensions |
|--------------------------------------|------------|
| **voyageai/voyage-4-large**          | 1024       |
| **voyageai/voyage-4**                | 1024       |
| **voyageai/voyage-4-lite**           | 1024       |
| **voyageai/voyage-code-4**           | 1024       |
| **voyageai/voyage-context-4**        | 1024       |
| **voyageai/voyage-context-3**        | 1024       |
| **voyageai/voyage-multimodal-3.5**   | 1024       |
| **voyageai/voyage-multimodal-3**     | 1024       |
| **voyageai/voyage-3.5**              | 1024       |
| **voyageai/voyage-3.5-lite**         | 512        |
| **voyageai/voyage-3-large**          | 1024       |
| **voyageai/voyage-3**                | 1024       |
| **voyageai/voyage-3-lite**           | 512        |
| **voyageai/voyage-code-3**           | 1024       |
| **voyageai/voyage-finance-2**        | 1024       |
| **voyageai/voyage-law-2**            | 1024       |
| **voyageai/voyage-large-2-instruct** | 1024       |
| **voyageai/voyage-multilingual-2**   | 1024       |
| **voyageai/voyage-code-2**           | 1536       |
| **voyageai/voyage-large-2**          | 1536       |
| **voyageai/voyage-2**                | 1024       |

{% hint style="info" %}
Contextualized models (`voyageai/voyage-context-4`, `voyageai/voyage-context-3`) are invoked through the VoyageAI by MongoDB `contextualized_embed` API. Epsilla embeds each input as its own independent document: the batch is passed as a flat `list[str]` with `enable_auto_chunking=true` and `chunk_size=32000`, so every string resolves to a single deterministic chunk and vector. Auto-chunking requires `input_type="document"`, so on the query path (`input_type="query"`) auto-chunking is not used.
{% endhint %}

For Epsilla open source vector db, you just need to add a header in the data ingestion and semantic search queries [like this](../../vector-database/embeddings.md#voyage-ai-embedding).

Then you can start using the voyageai embedding models during vector table schema creation:

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 12.10.07 PM.png" alt=""><figcaption></figcaption></figure>
