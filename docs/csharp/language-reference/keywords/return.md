---
title: return-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: a845ce257bf7f0cf0e64d6815b2278f6cec946e7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661614"
---
# <a name="return-c-reference"></a>return (C#-Referenz)

Die Anweisung `return` beendet die Ausführung der Methode, in der sie angezeigt wird, und gibt das Steuerelement an die aufrufende Methode zurück. Zudem kann ein optionaler Wert zurückgegeben werden. Wenn es sich bei der Methode um einen `void`-Typ handelt, kann die Anweisung `return` ausgelassen werden.

 Wenn sich die „return“-Anweisung in einem `try`-Block befindet, wird der `finally`-Block, falls vorhanden, ausgeführt bevor das Steuerelement an die aufrufende Methode zurückgegeben wird.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel gibt die Methode `CalculateArea()` die lokale Variable `area` als `double`-Wert zurück.

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [return-Anweisung](/cpp/cpp/return-statement-cpp)
