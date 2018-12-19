---
title: params-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: dd9699eb50f7dffc7c2f4976a79afbf689ba2470
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235841"
---
# <a name="params-c-reference"></a>params (C#-Referenz)

Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert.

Sie können eine durch Trennzeichen getrennte Liste der Argumente des in der Parameterdeklaration angegebenen Typs oder ein Array der Argumente des angegebenen Typs senden. Sie können auch auf das Senden von Argumenten verzichten. Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).

Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.

Der deklarierte Typ des `params`-Parameters muss wie im folgenden Beispiel gezeigt ein eindimensionales Array sein. Andernfalls tritt der Compilerfehler [CS0225](../../misc/cs0225.md) ein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden verschiedene Methoden veranschaulicht, in denen Argumente an einen `params`-Parameter gesendet werden können.

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Methodenparameter](method-parameters.md)