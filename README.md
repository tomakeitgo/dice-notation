# Dice Notation EBNF
    D                   := [Dd];
    Digits              := [0-9]+;
    Operator            := [+-];
    StatementTerminator := [;];

    numberOfSide        := digits;
    numberOfRolls       := digits;
    constant            := digits;

    expression          := constant
                        |  numberOfSides D numberOfRolls;
                        |  numberOfSides D numberOfRolls Operator constant;
                        ;

    complexExpression   := expression
                        |  expression Operator complexExpression
                        ;
                        
    statement           := complexExpression StatementTerminator;