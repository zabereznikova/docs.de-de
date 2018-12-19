---
title: continue-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: fbb5d170f10c0a4b6c6edeae6c3f4a549de65525
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243897"
---
# <a name="continue-c-reference"></a>continue (C#-Referenz)

Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) oder [foreach](../../../csharp/language-reference/keywords/foreach-in.md)-Anweisung, in der sie angegeben ist.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen. Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Rumpfs übersprungen.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [break-Anweisung](/cpp/cpp/break-statement-cpp)  
- [Sprunganweisungen](../../../csharp/language-reference/keywords/jump-statements.md)