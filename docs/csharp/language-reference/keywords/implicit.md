---
title: implicit (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- implicit
- implicit_CSharpKeyword
helpviewer_keywords:
- implicit keyword [C#]
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
ms.openlocfilehash: 70379136fd4b14403eac919ac15590250b17b416
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44213659"
---
# <a name="implicit-c-reference"></a>implicit (C#-Referenz)

Das `implicit`-Schlüsselwort wird verwendet, um einen impliziten benutzerdefinierten Typkonvertierungsoperator zu deklarieren. Verwenden Sie es zur Aktivierung impliziter Konvertierungen zwischen einem benutzerdefinierten Typ und einen anderen Typ, wenn die Konvertierung mit Sicherheit nicht zu einem Datenverlust führt.

## <a name="example"></a>Beispiel

[!code-csharp[csrefKeywordsConversion#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#5)]

Durch Eliminierung unnötiger Umwandlungen können implizite Konvertierungen die Lesbarkeit des Quellcodes verbessern. Da implizite Konvertierungen aber nicht erfordern, dass Programmierer explizit von einem Typ in den anderen umwandeln, muss darauf geachtet werden, um unerwartete Ergebnisse zu vermeiden. Im Allgemeinen sollten implizite Konvertierungsoperatoren keine Ausnahmen auslösen und keine Informationen verlieren, sodass sie problemlos ohne Wissen des Programmierers verwendet werden können. Wenn ein Konvertierungsoperator diese Kriterien nicht erfüllen kann, sollte er als `explicit` markiert werden. Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)  
- [C#-Programmierhandbuch](../../programming-guide/index.md)  
- [C#-Schlüsselwörter](index.md)  
- [explicit](explicit.md)  
- [Operator (C#-Referenz)](operator.md)  
- [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
