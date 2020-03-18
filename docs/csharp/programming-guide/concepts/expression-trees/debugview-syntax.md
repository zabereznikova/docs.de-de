---
title: Syntax der DebugView-Eigenschaft (C#)
description: Beschreibt die spezielle Syntax, die von der DebugView-Eigenschaft verwendet wird, um eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen zu erzeugen.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: ba695fc808108c49a4eee3c70a305b24c91769d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "67661714"
---
# <a name="debugview-syntax"></a>`DebugView`-Syntax

Die `DebugView`-Eigenschaft (nur beim Debuggen verfügbar) bietet eine Zeichenfolgendarstellung von Ausdrucksbaumstrukturen. Der größte Teil der Syntax ist recht einfach zu verstehen; einige Sonderfälle werden in den folgenden Abschnitten beschrieben.

Jedem Beispiel folgt ein Blockkommentar, der die `DebugView` enthält.

## <a name="parameterexpression"></a>ParameterExpression

Namen von <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType>-Variablen werden mit einem `$`-Symbol am Anfang angezeigt.

Wenn ein Parameter nicht über einen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `$var1` oder `$var2`.

### <a name="examples"></a>Beispiele

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a>ConstantExpression

Für <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>-Objekte, die ganzzahlige Werte, Zeichenfolgen und `null` darstellen, wird der Wert der Konstante angezeigt.

Für numerische Typen, die über Standardsuffixe als C#-Literale verfügen, wird das Suffix zum Wert hinzugefügt. Die folgende Tabelle zeigt die verschiedenen numerischen Typen und ihre zugeordneten Suffixe.

| Geben Sie Folgendes ein: | Schlüsselwort | Suffix |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [uint](../../../language-reference/builtin-types/integral-numeric-types.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [long](../../../language-reference/builtin-types/integral-numeric-types.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [ulong](../../../language-reference/builtin-types/integral-numeric-types.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [double](../../../language-reference/builtin-types/floating-point-numeric-types.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [float](../../../language-reference/builtin-types/floating-point-numeric-types.md) | F |
| <xref:System.Decimal?displayProperty=nameWithType> | [decimal](../../../language-reference/builtin-types/floating-point-numeric-types.md) | M |

### <a name="examples"></a>Beispiele

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a>BlockExpression

Wenn sich der Typ eines <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType>-Objekts vom Typ des letzten Ausdrucks im Block unterscheidet, wird der Typ in spitzen Klammern (`<` und `>`) angezeigt. Andernfalls wird der Typ des <xref:System.Linq.Expressions.BlockExpression>-Objekts nicht angezeigt.

### <a name="examples"></a>Beispiele

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a>LambdaExpression.

<xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType>-Objekte werden zusammen mit ihren Delegattypen angezeigt.

Wenn ein Lambda-Ausdruck über keinen Namen verfügt, wird ihm ein automatisch generierter Name zugewiesen, z.B. `#Lambda1` oder `#Lambda2`.

### <a name="examples"></a>Beispiele

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a>LabelExpression

Wenn Sie einen Standardwert für das <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>-Objekt angeben, wird dieser Wert vor dem <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>-Objekt angezeigt.

Das `.Label`-Token gibt den Anfang der Bezeichnung an. Das `.LabelTarget`-Token gibt den Zielort an, zu dem gewechselt werden soll.

Wenn eine Bezeichnung nicht über einen Namen verfügt, wird ihr ein automatisch generierter Name zugewiesen (z.B. `#Label1` oder `#Label2`).

### <a name="examples"></a>Beispiele

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a>Überprüfte Operatoren

Überprüften Operatoren wird in der Ansicht das `#`-Symbol vorangestellt. Der überprüfte Additionsoperator wird z.B. als `#+` angezeigt.

### <a name="examples"></a>Beispiele

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
