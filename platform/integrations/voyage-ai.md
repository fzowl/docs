# VoyageAI by MongoDB

On Epsilla Cloud, you can enable VoyageAI by MongoDB integration by providing your VoyageAI by MongoDB API key (we securely manage your keys using AWS KMS):

<figure><img src="../../.gitbook/assets/Screenshot 2024-05-18 at 8.52.45 AM.png" alt=""><figcaption></figcaption></figure>

## Embeddings

Epsilla integrates with VoyageAI by MongoDB with the following embedding models:

| Name                                 | Dimensions |
|--------------------------------------|------------|
| **voyageai/voyage-4-large**          | 1024       |
| **voyageai/voyage-4**                | 1024       |
| **voyageai/voyage-4-lite**           | 1024       |
| **voyageai/voyage-4-nano**           | 1024       |
| **voyageai/voyage-code-4**           | 1024       |
| **voyageai/voyage-context-4**        | 1024       |
| **voyageai/voyage-multimodal-3**     | 1024       |
| **voyageai/voyage-context-3**        | 1024       |
| **voyageai/voyage-3.5**              | 1024       |
| **voyageai/voyage-3.5-lite**         | 512        |
| **voyageai/voyage-3-large**          | 1024       |
| **voyageai/voyage-code-3**           | 1024       |
| **voyageai/voyage-finance-2**        | 1024       |
| **voyageai/voyage-law-2**            | 1024       |

## Contextual embeddings

The **voyageai/voyage-context-4** and **voyageai/voyage-context-3** models are contextualized chunk embedding models: each chunk is embedded with awareness of its surrounding document context. They are served through VoyageAI by MongoDB's `contextualized_embed` API (see the [official spec](https://docs.voyageai.com/docs/contextualized-chunk-embeddings)).

The `inputs` parameter accepts both supported formats:

```
inputs: Union[List[List[str]], List[str]]
```

- `List[List[str]]` — pre-chunked documents, one inner list of chunks per document.
- `List[str]` — a flat list of strings (a single document's chunks, queries, or full documents when auto-chunking is enabled).

```python
import voyageai

vo = voyageai.Client()

# Nested: one inner list of chunks per document
vo.contextualized_embed(
    inputs=[["chunk 1 of doc A", "chunk 2 of doc A"], ["chunk 1 of doc B"]],
    model="voyage-context-4",
    input_type="document",
)

# Flat: a single list of strings
vo.contextualized_embed(
    inputs=["chunk 1", "chunk 2", "chunk 3"],
    model="voyage-context-4",
    input_type="document",
)
```

For Epsilla open source vector db, you just need to add a header in the data ingestion and semantic search queries [like this](../../vector-database/embeddings.md#voyageai-by-mongodb-embedding).

Then you can start using the VoyageAI by MongoDB embedding models during vector table schema creation:

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-31 at 12.10.07 PM.png" alt=""><figcaption></figcaption></figure>
