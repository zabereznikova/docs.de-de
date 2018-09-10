---
title: Anonyme Methoden (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
ms.openlocfilehash: 26d4b7f46783b9aa41035775928a4fe322d0af44
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506656"
---
# <a name="anonymous-methods-c-programming-guide"></a>Anonyme Methoden (C#-Programmierhandbuch)
In Versionen von C# vor 2.0 bestand die einzige Möglichkeit zum Deklarieren eines [Delegaten](../../../csharp/language-reference/keywords/delegate.md) in der Verwendung von [benannten Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md). Mit C# 2.0 wurden anonyme Methoden eingeführt, und in C# 3.0 und höher lösen Lambdaausdrücke anonyme Methoden als bevorzugten Weg zum Schreiben von Inlinecode ab. Die Informationen zu anonymen Methoden in diesem Thema gelten jedoch auch für Lambdaausdrücke. In einem Fall bietet eine anonyme Methode eine Funktion, über die Lambdaausdrücke nicht verfügen. Anonyme Methoden ermöglichen das Auslassen der Parameterliste. Das bedeutet, dass eine anonyme Methode in Delegaten mit verschiedenen Signaturen konvertiert werden kann. Dies ist bei Lambdaausdrücken nicht möglich. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambdaausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Das Erstellen anonymer Methoden ist im Grunde genommen ein Weg, um einen Codeblock als Delegatparameter zu übergeben. Hier sind zwei Beispiele:  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 Mit anonymen Methoden verringern Sie den Mehraufwand an Codierung beim Instanziieren von Delegaten, da Sie keine separate Methode erstellen müssen.  
  
 So kann es nützlich sein, einen Codeblock anstatt eines Delegaten anzugeben, wenn das Erstellen einer Methode mit unnötigem Aufwand verbunden scheint. Ein gutes Beispiel ist das Starten eines neuen Threads. Diese Klasse erstellt einen Thread und enthält zudem den Code, den der Thread ausführt, ohne dass eine zusätzliche Methode für den Delegaten erstellt wird.  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Der Bereich der Parameter einer anonymen Methode ist der *anonyme Methodenblock*.  
  
 Es ist ein Fehler, wenn sich eine Sprunganweisung wie [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) oder [continue](../../../csharp/language-reference/keywords/continue.md) innerhalb des anonymen Methodenblocks befindet, wenn das Ziel außerhalb des Blocks liegt. Es ist auch ein Fehler, wenn sich eine Sprunganweisung wie `goto`, `break` oder `continue` außerhalb des anonymen Methodenblocks befindet, wenn das Ziel innerhalb des Blocks liegt.  
  
 Die lokalen Variablen und Parameter, deren Bereich eine anonyme Methodendeklaration enthält, werden als *äußere* Variablen der anonymen Methode bezeichnet. Beispielsweise ist im folgenden Codesegment `n` eine äußere Variable:  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 Ein Verweis auf die äußere Variable `n` gilt als *erfasst*, wenn der Delegat erstellt wird. Anders als bei lokalen Variablen erstreckt sich die Lebensdauer einer erfassten Variablen so lange, bis die Delegaten, die auf die anonymen Methoden verweisen, für die automatische Speicherbereinigung verfügbar sind.  
  
 Eine anonyme Methode kann nicht auf die Parameter [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) eines äußeren Bereichs zugreifen.  
  
 Auf unsicheren Code kann nicht innerhalb des *anonymen Methodenblocks* zugegriffen werden.  
  
 Anonyme Methoden sind auf der linken Seite des [is](../../../csharp/language-reference/keywords/is.md)-Operators nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, um einen Delegaten zu instanziieren:  
  
-   Zuordnen des Delegaten zu einer anonymen Methode.  
  
-   Zuordnen des Delegaten zu einer benannten Methode (`DoWork`).  
  
 In beiden Fällen wird eine Meldung angezeigt, wenn der Delegat aufgerufen wird.  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Delegaten](../../../csharp/programming-guide/delegates/index.md)  
- [Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [Delegate mit benannten im Vergleich zu anonymen Methoden](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
