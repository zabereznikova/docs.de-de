---
title: Syntax von DebugView-Eigenschaft (Visual Basic) verwendet wird
description: Beschreibt die spezielle Syntax, die durch die DebugView-Eigenschaft verwendet wird, um eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen zu erstellen.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: ae2c75607f7b9cdc40fc5c163ce533f0472ab454
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689540"
---
# <a name="debugview-syntax"></a>`DebugView`-Syntax

Die `DebugView` Eigenschaft (nur beim Debuggen verfügbar) bietet eine Darstellung der Zeichenfolge von Ausdrucksbaumstrukturen. Die meisten der Syntax ist recht einfach zu verstehen. besondere Fälle werden in den folgenden Abschnitten beschrieben.

Jedes Beispiel folgt eine Comment-Block mit der `DebugView`.

## <a name="parameterexpression"></a>ParameterExpression

Namen von <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType>-Variablen werden mit einem „$“-Symbol am Anfang angezeigt.

Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.

### <a name="examples"></a>Beispiele

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a>ConstantExpressions

Für <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.

Für einige numerische Typen wird der Wert ein Suffix hinzugefügt:

| Typ | Stichwort | Suffix |
|--|--|--|
| <xref:System.UInt32> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | U |
| <xref:System.Int64> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double> | [Double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single> | [Single](../../../language-reference/data-types/single-data-type.md) | F |
| <xref:System.Decimal> | [Decimal](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>Beispiele

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a>BlockExpression

Wenn der Typ des eine <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> Objekt vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in spitzen Klammern angezeigt (`<` und `>`). Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.

### <a name="examples"></a>Beispiele

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object),
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a>LambdaExpression.

<xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType>-Objekte werden zusammen mit ihren Delegattypen angezeigt.

Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.

### <a name="examples"></a>Beispiele

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a>LabelExpression

Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>-Objekt angezeigt.

Das `.Label`-Token gibt den Anfang der Bezeichnung an. Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.

Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).

### <a name="examples"></a>Beispiele

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a>Überprüfte Operatoren

Überprüfte Operatoren werden angezeigt, mit der `#` Ansicht das Symbol. Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.

### <a name="examples"></a>Beispiele

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```
