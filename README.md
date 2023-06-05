# Step 1 : Creating a virtual environment
## Install package virtualenv
```
py -m pip install --user virtualenv
py -m venv env
```

## Activate environment
```
.\env\Scripts\activate
```

# Step 2 : Install FastAPI and Uvicorn
```
pip install fastapi
pip install "uvicorn[standard]"
```

# Step3 : Create the main.py file
```Python
from typing import Union

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}

``` 

# Step 4 : Run the server
```
uvicorn main:app --reload
```

# Step 5 : Create a get method with parameters
```Python
@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q": q}
```

# Step 6 : Make a request
Write in your navigator :
```
127.0.0.1:8000/items/5?q=myquerry
```
And see the response

# Step 7 : Interactive documentation
```
127.0.0.1:8000/docs
```