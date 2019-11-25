---
title: Syntax used by DebugView property
description: Beschreibt die spezielle Syntax, die von der DebugView-Eigenschaft verwendet wird, um eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen zu erzeugen.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 98ceba37aa226fab68ae1c1028e2a1139b3b8e7e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346868"
---
# <a name="debugview-syntax"></a>`DebugView`-Syntax

Die `DebugView`-Eigenschaft (nur beim Debuggen verfügbar) bietet eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen. Der größte Teil der Syntax ist recht einfach zu verstehen; einige Sonderfälle werden in den folgenden Abschnitten beschrieben.

Each example is followed by a comment block containing the `DebugView`.

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

For some numeric types, a suffix is added to the value:

| Geben Sie Folgendes ein: | Stichwort | Suffix |
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

Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in spitzen Klammern (`<` und `>`) angezeigt. Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.

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

Überprüften Operatoren wird in der Ansicht das `#`-Symbol vorangestellt. Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.

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
