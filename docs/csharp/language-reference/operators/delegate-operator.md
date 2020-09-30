---
description: Operator „delegate“ – C#-Referenz
title: Operator „delegate“ – C#-Referenz
ms.date: 09/25/2020
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: db2bf673db12e4a10741a26112820726a4b8aaee
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247656"
---
# <a name="delegate-operator-c-reference"></a>Operator „delegate“ (C#-Referenz)

Der Operator `delegate` erstellt eine anonyme Methode, die in einen Delegattyp konvertiert werden kann:

[!code-csharp-interactive[anonymous method](snippets/shared/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Ab C# 3 bieten Lambdaausdrücke eine präzisere und aussagekräftigere Möglichkeit zum Erstellen anonymer Funktionen. Verwenden Sie den [Operator „=>“](lambda-operator.md), um einen Lambdaausdruck zu erstellen:
>
> [!code-csharp-interactive[lambda expression](snippets/shared/DelegateOperator.cs#Lambda)]
>
> Weitere Informationen zu Features von Lambdaausdrücken (etwa zum Erfassen äußerer Variablen) finden Sie unter [Lambdaausdrücke](lambda-expressions.md).

Bei Verwendung des Operators `delegate` können Sie die Parameterliste weglassen. Die erstellte anonyme Methode kann dann mit einer beliebigen Parameterliste in einen Delegattyp konvertiert werden, wie im folgenden Beispiel zu sehen:

[!code-csharp-interactive[no parameter list](snippets/shared/DelegateOperator.cs#WithoutParameterList)]

Dies ist die einzige Funktion anonymer Methoden, die von Lambdaausdrücken nicht unterstützt wird. In allen anderen Fällen ist ein Lambdaausdruck eine bevorzugte Methode zum Schreiben von Inlinecode.

Ab C# 9.0 können Sie [discards](../../discards.md) verwenden, um mindestens zwei Eingabeparameter einer anonymen Methode anzugeben, die nicht von der Methode verwendet werden:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetDiscards" :::

Aus Gründen der Abwärtskompatibilität wird `_` als Name dieses Parameters innerhalb einer anonymen Methode behandelt, wenn nur ein einzelner Parameter den Namen `_` aufweist.

Ab C# 9.0 können Sie außerdem den `static`-Modifizierer bei der Deklaration einer anonymen Methode verwenden:

:::code language="csharp" source="snippets/shared/DelegateOperator.cs" id="SnippetStatic" :::

Eine statische anonyme Methode kann keine lokalen Variablen oder den Instanzstatus aus einschließenden Bereichen erfassen.

Zum Deklarieren eines [Delegattyps](../builtin-types/reference-types.md#the-delegate-type) wird auch das Schlüsselwort `delegate` verwendet.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
- [=>-Operator](lambda-operator.md)
