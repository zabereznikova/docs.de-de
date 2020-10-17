---
description: continue-Anweisung – C#-Referenz
title: continue-Anweisung – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877651"
---
# <a name="continue-c-reference"></a>continue (C#-Referenz)

Die `continue`-Anweisung übergibt die Steuerung an die nächste Iteration der einschließenden [while](./while.md), [do](./do.md), [for](./for.md) oder [foreach](./foreach-in.md)-Anweisung, in der sie angegeben ist.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Zähler initialisiert, um von 1 bis 10 zu zählen. Indem die `continue`-Anweisung in Verbindung mit dem `(i < 9)`-Ausdruck verwendet wird, werden die Anweisungen zwischen `continue` und dem Ende des `for`-Teils in Iterationen übersprungen, in denen `i` weniger als 9 beträgt. In den letzten beiden Iterationen der `for`-Schleife, für die i == 9 und i == 10 gilt, wird die `continue`-Anweisung nicht ausgeführt, und der Wert von `i` wird in der Konsole zurückgegeben.

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [break-Anweisung](/cpp/cpp/break-statement-cpp)
