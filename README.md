# dice-notation

## Dice Notation EBNF
    D                 := [Dd];
    Digit             := [0-9];
    Operator          := [+-];

    numberOfSide      := digit+;
    numberOfRolls     := digit+;
    constant          := digit+;

    expression        := constant
                      |  numberOfSides D numberOfRolls;
                      |  numberOfSides D numberOfRolls Operator constant;
                      ;

    complexExpression := expression
                      |  expression Operator complexExpression
                      ;
