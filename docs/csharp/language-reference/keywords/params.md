---
description: params-Schlüsselwort für Parameterarrays – C#-Referenz
title: params-Schlüsselwort für Parameterarrays – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134470"
---
# <a name="params-c-reference"></a>params (C#-Referenz)

Mithilfe des Schlüsselworts `params` kann ein [Methodenparameter](method-parameters.md) angegeben werden, der eine variable Anzahl von Argumenten akzeptiert. Der Parametertyp muss ein eindimensionales Array sein.

Nach dem `params`-Schlüsselwort sind keine zusätzlichen Parameter in einer Methodendeklaration zugelassen. Gleichzeitig ist nur ein `params`-Schlüsselwort in einer Methodendeklaration zulässig.

Wenn der deklarierte Typ des `params`-Parameters kein eindimensionales Array ist, tritt der Compilerfehler [CS0225](../../misc/cs0225.md) auf.

Wenn Sie eine Methode mit einem `params`-Parameter aufrufen, können Sie Folgendes übergeben:

- Eine durch Trennzeichen getrennte Liste von Argumenten des Typs der Arrayelemente
- Ein Array aus Argumenten des angegebenen Typs
- Keine Argumente. Wenn Sie keine Argumente senden, ist die Länge der `params`-Liste 0 (null).

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
