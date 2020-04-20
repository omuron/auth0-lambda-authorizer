# auth0-lambda-authorizer

## build

```
sam build
```

## package

```
sam package --s3-bucket auth0-nodejs10-artifacts --output-template-file packaged.yaml
```

## deploy

```
sam deploy \
    --template-file packaged.yaml \
    --stack-name auth0-nodejs10-stack \
    --capabilities CAPABILITY_IAM \
    --parameter-overrides \
        JwksUri=${JWKS_URI} \
        Audience=${AUDIENCE} \
        TokenIssuer=${TOKEN_ISSUER}
```
