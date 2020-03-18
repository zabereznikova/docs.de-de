---
title: partial-Methode – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 62efd8b47fb565316b417a65e1b0fe37e40786c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713221"
---
# <a name="partial-method-c-reference"></a>partial-Methode (C#-Referenz)

Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert. Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können. Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung. Die folgenden Bedingungen gelten für partielle Methoden:

- Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.

- Die Methode muss "void" zurückgeben.

- Es sind keine Zugriffsmodifizierer zulässig. Partielle Methoden sind implizit privat.

Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [partial-Typ](partial-type.md)
