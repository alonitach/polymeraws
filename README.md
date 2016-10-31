## \<aws-app\>

The aws-app element is used for initializing and configuring your
connection to AWS.


## \<aws-dynamodb\>

The `aws-dynamodb` element is an easy way to interact with a AWS DynamoDB
database. as an object and expose it to the Polymer databinding system.

Example usage:

```html
<aws-app
    region="eu-west-1">
</aws-app>
<aws-dynamodb
    table="notes"
    data="{{data}}">
</aws-dynamodb>
```

This fetches the `data` object from the `notes` table in the DynamoDB
database and exposes it to the Polymer databinding system. Changes to
`data` will likewise be sent back and stored.


## \<aws-lambda\>

The `aws-lambda` element is an easy way to invoke a AWS Lambda function.

Example usage:

```html
<aws-app
    region="eu-west-1">
</aws-app>
<aws-lambda
    id="transformNotes"
    function-name="transformNotes"
    on-response="handleResponse">
</aws-lambda>
```

The `aws-app` element initializes `AWS` in `aws-lambda`.

JavaScript invoke calls can then be made to the `aws-lambda` object to invoke
the Lambda function.

```javascript
this.$.transformNotes.invoke();
```
