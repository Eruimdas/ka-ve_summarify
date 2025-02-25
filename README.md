# ka-ve_summarify

## Takım Üyeleri

- Yunus Emre Gündoğmuş [@yemregundogmus](https://github.com/yemregundogmus)
- Feyza Zeynep Salam [@feyzazeynep](https://github.com/feyzazeynep)
- Emre Yüksel [@emreeyukseel](https://github.com/emreeyukseel)
- Büşra Gökmen [@newsteps8](https://github.com/newsteps8)
- Hasan Kemik [@eruimdas](https://github.com/Eruimdas)

## Kullanım
## Türkçe Metin Özetleme ve Ka|Ve Stemmer
### Gerekli Kütüphaneler

```python
import pandas as pd
import numpy as np
from nltk.corpus import stopwords
import heapq
from gensim.summarization import keywords
from nltk import sent_tokenize
from sklearn.metrics.pairwise import cosine_similarity
from gensim.models import KeyedVectors
import networkx as nx
import re
import numpy as np
import json
import pickle
from keras.models import model_from_json
from keras.models import load_model
import Extraction_Based_Text_Summarization
```

Yukarıdaki kütüphaneleri programınıza ekledikten sonra,

```python
ex_sum = extraction_based_sum()
```
kodu ile class'ı çağırabilir. Sonrasında elinizde özetlenmesini istediğiniz veri ile

```python
ex_sum.get_sentences(text,k)
```

`k` kadar cümleyi metinden alabilirsiniz. Anahtar kelime çıkarımı için ise,

```python
ex_sum.get_keywords(text,ratio)
```
kodunu kullanarak, metindeki kelime sayısının oranı kadar anahtar kelime alabilirsiniz. Bu sayıyı `ratio` değeri ile kontrol edebilirsiniz.

## Doc2Vec Method
### Gerekli Kütüphaneler
```python
import pandas as pd
import re
import numpy as np
import gensim
```
Kütüphaneler eklendikten sonra, önceden eğitilmiş Word2Vec modeliyle[2] Döküman benzerliği class'ımızı çalıştırıyoruz. 

```python
ds = DocSim(w2v_model,stopwords)
```
Sonrasında ise, elimizdeki dökümana en çok benzeyen 10 dökümanı sıralamak için aşağıdaki satırı çalıştırıyoruz.
```python
sim_scores = ds.calculate_similarity(source_doc, target_docs)
```

## Flask API

Flask API'sini kullanabilmek için ilk önce bir sanal flask ortamı oluşturmanız gerekiyor. Sonrasında ise aşağıda belirtilen kütüphaneleri kurmanız gerekmekte:

```python
import pandas as pd
import numpy as np
from bs4 import BeautifulSoup as bs
import requests 
import datetime
from nltk.corpus import stopwords
import heapq
from gensim.summarization import keywords
from nltk import sent_tokenize
from sklearn.metrics.pairwise import cosine_similarity
import networkx as nx
import re
import json
import pickle
from keras.models import model_from_json
from keras.models import load_model
from gensim.models import KeyedVectors
from gensim.corpora.wikicorpus import WikiCorpus
from gensim.models.doc2vec import Doc2Vec, TaggedDocument
from gensim.models import Doc2Vec
import tensorflow as tf
```

Kütüphaneleri kurduktan sonra, `python main.py`komutunu çalıştırarak, ürünü demo hâlinde deneyebilirsiniz.

## Veri Çekme / Oluşturma

`Examples` klasöründe bulunan `hürriyetScraper` dosyasından hurriyet.com.tr sitesi üzerinde haberleri çekerek, kendi verisetinizi oluşturabilir, bu örneği kullanarak TsCorpus üzerinden elinizdeki veriyi parçalayacak bir scraper yazabilirsiniz.

## Referanslar
- [1] https://github.com/deeplearningturkiye/kelime_kok_ayirici
- [2] https://github.com/akoksal/Turkish-Word2Vec
- [3] https://github.com/Eruimdas/turkish_text_summarization
- [4] https://tscorpus.com

# Demo Video

<div align="center">
  <a href="https://www.youtube.com/watch?v=s4OcbfcnD-c"><img src="https://img.youtube.com/vi/s4OcbfcnD-c/0.jpg" alt="Demo Video"></a>
</div>

### ----------------------------------------------------------------------------------------------

## Team Members

- Yunus Emre Gündoğmuş [@yemregundogmus](https://github.com/yemregundogmus)
- Feyza Zeynep Salam [@feyzazeynep](https://github.com/feyzazeynep)
- Emre Yüksel [@emreeyukseel](https://github.com/emreeyukseel)
- Büşra Gökmen [@newsteps8](https://github.com/newsteps8)
- Hasan Kemik [@eruimdas](https://github.com/Eruimdas)

## How to use
## Turkish Text Summarization and Ka|Ve Stemmer
### Necessary Libraries

```python
import pandas as pd
import numpy as np
from nltk.corpus import stopwords
import heapq
from gensim.summarization import keywords
from nltk import sent_tokenize
from sklearn.metrics.pairwise import cosine_similarity
from gensim.models import KeyedVectors
import networkx as nx
import re
import numpy as np
import json
import pickle
from keras.models import model_from_json
from keras.models import load_model
import Extraction_Based_Text_Summarization
```

After you've added those libraries,

```python
ex_sum = extraction_based_sum()
```
you can use the class with that code, and after that, with the text you want to be summarized,

```python
ex_sum.get_sentences(text,k)
```

you can take the best `k` sentences from it. For keyword extraction,

```python
ex_sum.get_keywords(text,ratio)
```
with the code above, you can get keywords according to the ratio of the word count in the text. You can control that by changing `ratio` value.

## Doc2Vec Method
### Necessary Libraries
```python
import pandas as pd
import re
import numpy as np
import gensim
```
After importing the libraries, using the pre-trained Word2Vec model for Turkish[2], we've created our similarity model.

```python
ds = DocSim(w2v_model,stopwords)
```
After that, using the code below, we've listed the most similar 10 documents to the document we've entered.
```python
sim_scores = ds.calculate_similarity(source_doc, target_docs)
```

## Flask API

In order to use Flask, you first need to create a virtual flask environment in order to avoid any conflict. The libraries used are as follows:
```python
import pandas as pd
import numpy as np
from bs4 import BeautifulSoup as bs
import requests 
import datetime
from nltk.corpus import stopwords
import heapq
from gensim.summarization import keywords
from nltk import sent_tokenize
from sklearn.metrics.pairwise import cosine_similarity
import networkx as nx
import re
import json
import pickle
from keras.models import model_from_json
from keras.models import load_model
from gensim.models import KeyedVectors
from gensim.corpora.wikicorpus import WikiCorpus
from gensim.models.doc2vec import Doc2Vec, TaggedDocument
from gensim.models import Doc2Vec
import tensorflow as tf
```

After downloading the libraries, you can use the live dome by running the code: `python main.py

## Data Scraping
In the `Examples` folder, in `hurriyetScraper` file, you can find our scraper for hurriyet.com.tr. From this file,you can scrape your own dataset, and by referencing it you can write your own TsCorpus scraper for further analysis.

## References
- [1] https://github.com/deeplearningturkiye/kelime_kok_ayirici
- [2] https://github.com/akoksal/Turkish-Word2Vec
- [3] https://github.com/Eruimdas/turkish_text_summarization
- [4] https://tscorpus.com

# Demo Video

<div align="center">
  <a href="https://www.youtube.com/watch?v=s4OcbfcnD-c"><img src="https://img.youtube.com/vi/s4OcbfcnD-c/0.jpg" alt="Demo Video"></a>
</div>
