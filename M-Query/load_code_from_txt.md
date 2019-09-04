# Load Code from Text File

<https://blog.crossjoin.co.uk/2014/02/04/loading-power-query-m-code-from-text-files/>

``` PowerBI
let
    //Load M code from text file
    Source = Text.FromBinary(File.Contents("C:\PowerQueryQueries\DynamicQuery.txt")),
    //Evaluate the code from the file as an M expression
    EvaluatedExpression = Expression.Evaluate(Source, #shared)
in
    EvaluatedExpression
```