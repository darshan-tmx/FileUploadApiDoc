# 1. Get temporary Token

## Query

###### Query string

```
{
  token: getTemporaryToken
}
```

###### Headers - this is as usual hidden token that is being shared

```
{
  "authorization": "A6lsIJ&02lpGkc23OKw$Dy234aF233!Mn"
}
```

## Output

```
{
  "data": {
    "token": "rjgAMzNTIO9VE47tyJYnxcK3PvpfuUD8BZ0S"
  }
}
```

<br/>
<br/>

# 2. Mutation - Similar as today

## Query

###### Query string

###### 2 Differences

###### - Name change of the query

###### - authoriazation token will always change

```
mutation uploadPdfWithTemporaryToken($symbols: [String]!, $title: String!, $file: String!, $externalUserId:String!) {
    uploadPdfWithTemporaryToken(symbols: $symbols, title: $title, file: $file,externalUserId: $externalUserId) {
      id
      type
      symbol
      title
      url
      createdAt
      updatedAt
    }
}
```

###### Headers - this token will be same as the output of the first query

```
{
  "authorization": "rjgAMzNTIO9VE47tyJYnxcK3PvpfuUD8BZ0S"
}
```

## Output

```
{
  "data": {
    "uploadPdfWithTemporaryToken": [
      {
        "id": 966,
        "type": "document",
        "symbol": "TD",
        "title": "do not know",
        "url": "http://localhost:3000/companyFiles/TD/d201eaec-d159-410c-b0ca-3e5dbffc32cf.pdf",
        "createdAt": "1669175859146",
        "updatedAt": "1669175859146"
      },
      {
        "id": 967,
        "type": "document",
        "symbol": "X",
        "title": "do not know",
        "url": "http://localhost:3000/companyFiles/X/61a85872-eb1b-4f1e-b7ff-9f8607a8fb31.pdf",
        "createdAt": "1669175859147",
        "updatedAt": "1669175859147"
      }
    ]
  }
}
```
