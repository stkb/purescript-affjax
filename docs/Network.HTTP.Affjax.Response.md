## Module Network.HTTP.Affjax.Response

#### `ResponseType`

``` purescript
data ResponseType a
  = ArrayBufferResponse
  | BlobResponse
  | DocumentResponse
  | JSONResponse
  | StringResponse
```

Valid response types for an AJAX request. This is used to determine the
`ResponseContent` type for a request. The `a` type variable is a phantom
type used to associate the `ResponseType` with a particular instance of
`Respondable`.

##### Instances
``` purescript
instance eqResponseType :: Eq (ResponseType a)
instance showResponseType :: Show (ResponseType a)
```

#### `responseTypeToString`

``` purescript
responseTypeToString :: forall a. ResponseType a -> String
```

#### `ResponseContent`

``` purescript
type ResponseContent = Foreign
```

Type representing content types that be received from an XHR request
(Blob, Document, JSON, String).

#### `Respondable`

``` purescript
class Respondable a where
  responseType :: ResponseType a
  fromResponse :: ResponseContent -> F a
```

##### Instances
``` purescript
instance responsableBlob :: Respondable Blob
instance responsableDocument :: Respondable Document
instance responsableJSON :: Respondable Foreign
instance responsableString :: Respondable String
instance responsableUnit :: Respondable Unit
```


