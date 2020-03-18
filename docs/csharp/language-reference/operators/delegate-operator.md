---
title: Operator „delegate“ – C#-Referenz
ms.date: 07/18/2019
helpviewer_keywords:
- delegate [C#]
- anonymous method [C#]
ms.openlocfilehash: 1dd27fe5fdfdc1bc8a63e1298da00d252e800a72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847338"
---
# <a name="delegate-operator-c-reference"></a>Operator „delegate“ (C#-Referenz)

Der Operator `delegate` erstellt eine anonyme Methode, die in einen Delegattyp konvertiert werden kann:

[!code-csharp-interactive[anonymous method](snippets/DelegateOperator.cs#AnonymousMethod)]

> [!NOTE]
> Ab C# 3 bieten Lambdaausdrücke eine präzisere und aussagekräftigere Möglichkeit zum Erstellen anonymer Funktionen. Verwenden Sie den [Operator „=>“](lambda-operator.md), um einen Lambdaausdruck zu erstellen:
>
> [!code-csharp-interactive[lambda expression](snippets/DelegateOperator.cs#Lambda)]
>
> Weitere Informationen zu Features von Lambdaausdrücken (etwa zum Erfassen äußerer Variablen) finden Sie unter [Lambdaausdrücke](../../programming-guide/statements-expressions-operators/lambda-expressions.md).

Bei Verwendung des Operators `delegate` können Sie die Parameterliste weglassen. Die erstellte anonyme Methode kann dann mit einer beliebigen Parameterliste in einen Delegattyp konvertiert werden, wie im folgenden Beispiel zu sehen:

[!code-csharp-interactive[no parameter list](snippets/DelegateOperator.cs#WithoutParameterList)]

Dies ist die einzige Funktion anonymer Methoden, die von Lambdaausdrücken nicht unterstützt wird. In allen anderen Fällen ist ein Lambdaausdruck eine bevorzugte Methode zum Schreiben von Inlinecode.

Zum Deklarieren eines `delegate`Delegattyps[ wird auch das Schlüsselwort ](../builtin-types/reference-types.md#the-delegate-type) verwendet.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Anonyme Funktionsausdrücke](~/_csharplang/spec/expressions.md#anonymous-function-expressions) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [=>-Operator](lambda-operator.md)
