# Audios — vectorai 0.1.0 documentation

 [vectorai]()

## Audios[¶]()

### Audios[¶]()

Audios _class_ `vectorai.api.audio.ViAudioClient`\(_username_, _api\_key_, _url=None_\)[¶]()

Search and Encoding of Audios `search_audio`\(_collection\_name: str_, _audio_, _fields: List_, _metric: str = 'cosine'_, _min\_score=None_, _page: int = 1_, _page\_size: int = 10_, _include\_vector: bool = False_, _include\_count: bool = True_, _asc: bool = False_\)[¶]()

Search an audio field with audio using Vector Search Vector similarity search with an audio directly.

\_note: audio has to be stored somewhere and be provided as audio\_url, a url that stores the [audio\_]()

For example: an audio\_url represents sounds that a pokemon make:

```text
"https://play.pokemonshowdown.com/audio/cries/pikachu.mp3"

-> <Encode the audio to vector> ->

audio vector: [0.794617772102356, 0.3581121861934662, 0.21113917231559753, 0.24878688156604767, 0.9741804003715515 ...]

-> <Vector Search> ->

Search Results: {...}
```

Parameters

* **audio\_url** – The audio url of an audio to encode into a vector
* **collection\_name** – Name of Collection
* **search\_fields** – Vector fields to search through
* **approx** – Used for approximate search
* **sum\_fields** – Whether to sum the multiple vectors similarity search score as 1 or seperate
* **page\_size** – Size of each page of results
* **page** – Page of the results
* **metric** – Similarity Metric, choose from \[‘cosine’, ‘l1’, ‘l2’, ‘dp’\]
* **min\_score** – Minimum score for similarity metric
* **include\_vector** – Include vectors in the search results
* **include\_count** – Include count in the search results
* **hundred\_scale** –

  Whether to scale up the metric by 100asc:

  Whether to sort the score by ascending order \(default is false, for getting most similar results\)

 `search_audio_by_upload`\(_collection\_name: str_, _audio_, _fields: List_, _metric: str = 'cosine'_, _min\_score=None_, _page: int = 1_, _page\_size: int = 10_, _include\_vector: bool = False_, _include\_count: bool = True_, _asc: bool = False_\)[¶]()

Search an audio field with uploaded audio using Vector Search with an uploaded audio directly.

\_note: audio has to be sent as a base64 encoded [string\_]()Parameters

* **collection\_name** – Name of Collection
* **search\_fields** – Vector fields to search against
* **page\_size** – Size of each page of results
* **page** – Page of the results
* **approx** – Used for approximate search
* **sum\_fields** – Whether to sum the multiple vectors similarity search score as 1 or seperate
* **metric** – Similarity Metric, choose from \[‘cosine’, ‘l1’, ‘l2’, ‘dp’\]
* **min\_score** – Minimum score for similarity metric
* **include\_vector** – Include vectors in the search results
* **include\_count** – Include count in the search results
* **hundred\_scale** – Whether to scale up the metric by 100
* **audio** –

  Audio in local file pathasc:

  Whether to sort the score by ascending order \(default is false, for getting most similar results\)

 `encode_audio`\(_collection\_name: str_, _audio_\)[¶]()

Encode encode into a vector

\_note: audio has to be stored somewhere and be provided as audio\_url, a url that stores the [audio\_]()

For example: an audio\_url represents sounds that a pokemon make:

```text
"https://play.pokemonshowdown.com/audio/cries/pikachu.mp3"

-> <Encode the audio to vector> ->

audio_url vector: [0.794617772102356, 0.3581121861934662, 0.21113917231559753, 0.24878688156604767, 0.9741804003715515 ...]
```

Parameters

* **audio\_url** – The audio url of an audio to encode into a vector
* **collection\_name** – Name of Collection

 `encode_audio_job`\(_collection\_name: str_, _audio\_field: str_, _refresh: bool = False_\)[¶]()

Encode all audios in a field into vectors

Within a collection encode the specified audio field in every document into vectors.

\_note: audio has to be stored somewhere and be provided as audio\_url, a url that stores the [audio\_]()

For example, an audio\_url field “pokemon\_cries” represents sounds that a pokemon make:

```text
document 1 audio_url field: {"pokemon_cries" : "https://play.pokemonshowdown.com/audio/cries/pikachu.mp3"}

document 2 audio_url field: {"pokemon_cries" : "https://play.pokemonshowdown.com/audio/cries/meowth.mp3"}

-> <Encode the audios to vectors> ->

document 1 audio_url vector: {"pokemon_cries_vector_": [0.794617772102356, 0.3581121861934662, 0.21113917231559753, 0.24878688156604767, 0.9741804003715515 ...]}

document 2 audio_url vector: {"pokemon_cries_vector_": [0.8364648222923279, 0.6280597448348999, 0.8112713694572449, 0.36105549335479736, 0.005313870031386614 ...]}
```

Parameters

* **audio\_field** – The audio field to encode into vectors
* **refresh** – Whether to refresh the whole collection and re-encode all to vectors
* **collection\_name** – Name of Collection

