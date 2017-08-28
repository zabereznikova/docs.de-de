---
title: Lokale Funktionen (C#-Programmierhandbuch)
ms.date: 2017-06-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- local functions [C#]
author: rpetrusha
ms.author: ronpet
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5a4b84756be7d33c478d8115b812795dba182cdf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="local-functions-c-programming-guide"></a>Lokale Funktionen (C#-Programmierhandbuch)

Ab C#-7 unterstützt C# *lokale Funktionen*. Lokale Funktionen sind private Methoden eines Typs, die in einem anderen Member geschachtelt sind. Sie können nur aus ihrem enthaltenden Member aufgerufen werden. Lokale Funktionen können deklariert und aufgerufen werden aus:

- Methoden, insbesondere Iteratormethoden und Async-Methoden
- Konstruktoren
- Eigenschaftenaccessoren
- Ereignisaccessoren
- Anonymen Methoden
- Lambdaausdrücke
- Finalizer
- Anderen lokalen Funktionen

Lokale Funktionen können jedoch nicht in einem Ausdruckskörpermember deklariert werden.

> [!NOTE]
> In einigen Fällen können Sie einen Lambdaausdruck zum Implementieren von Funktionen verwenden, die auch von einer lokalen Funktion unterstützt werden. Einen Vergleich finden Sie unter [Lokale Funktionen im Vergleich zu Lambdaausdrücken](../../local-functions-vs-lambdas.md).

Lokale Funktionen machen den Zweck Ihres Codes deutlich. Beim Lesen des Codes wird deutlich, dass die Methode nur von der enthaltenden Methode aufgerufen werden kann. Bei Teamprojekten wird auch verhindert, dass ein anderer Entwickler die Methode versehentlich direkt an anderer Stelle in der Klasse aufruft.
 
## <a name="local-function-syntax"></a>Syntax einer lokalen Funktion

Eine lokale Funktion wird definiert als eine geschachtelte Methode in einem enthaltenden Member. Ihre Definition besitzt die folgende Syntax:

```txt
<modifiers: async | unsafe> <return-type> <method-name> <parameter-list>
```

Lokale Funktionen können die Modifizierer [async](../../language-reference/keywords/async.md) und [unsafe](../../language-reference/keywords/unsafe.md) verwenden. 

Beachten Sie, dass alle im enthaltenden Member definierten lokalen Variablen, einschließlich der Methodenparameter, in der lokalen Funktion zugänglich sind. 

Im Gegensatz zu einer Methodendefinition kann die Definition einer lokalen Funktion keines der folgenden Elemente enthalten:

- Den Zugriffsmodifizierer für Member. Da alle lokale Funktionen privat sind, generiert das Verwenden eines Zugriffsmodifizierers wie etwa das Schlüsselwort `private` den Compilerfehler CS0106 „Der Modifizierer ‚private‘ ist für dieses Element nicht gültig“.
 
- Das Schlüsselwort [static](..\..\language-reference\keywords\static.md). Die Verwendung des Schlüsselworts `static` generiert den Compilerfehler CS0106 „Der Modifizierer ‚static‘ ist für dieses Element nicht gültig“.

Darüber hinaus können keine Attribute auf lokale Funktionen oder ihre Parameter und Typparameter angewendet werden. 
 
Das folgende Beispiel definiert eine lokale Funktion mit dem Namen `AppendPathSeparator`, die für eine Methode mit dem Namen `GetText` privat ist:
   
[!code-cs[LokaleFunktionBeispiel](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  
   
## <a name="local-functions-and-exceptions"></a>Lokale Funktionen und Ausnahmen

Eine nützliche Funktion von lokalen Funktionen ist die Tatsache, dass sie Ausnahmen sofort verfügbar machen können. Bei Methodeniteratoren werden Ausnahmen erst eingeblendet, wenn die zurückgegebene Sequenz aufgelistet wird, und nicht, wenn der Iterator abgerufen wird. Bei async-Methoden werden Ausnahmen festgestellt, wenn die zurückgegebene Aufgabe erwartet wird. 

Das folgende Beispiel definiert eine `OddSequence`-Methode, die ungerade Zahlen in einem angegebenen Bereich aufzählt. Da eine Zahl größer als 100 an die `OddSequence`-Enumeratormethode übergeben wird, wird <xref:System.ArgumentOutOfRangeException> ausgelöst. Die Ausgabe des Beispiels zeigt, dass die Ausnahme erst beim Durchlaufen der Zahlen und nicht beim Abrufen des Enumerators eingeblendet wird.

[!code-cs[LokaleFunktionIterator1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)] 

Stattdessen können Sie während der Validierung und vor Abrufen des Iterators wie im folgenden Beispiel dargestellt eine Ausnahme auslösen, indem der Iterator aus einer lokalen Funktion zurückgegeben wird.

[!code-cs[LokaleFunktionIterator2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

Lokale Funktionen können auf ähnliche Weise verwendet werden, um Ausnahmen außerhalb des asynchronen Vorgangs zu behandeln. Normalerweise erfordern Ausnahmen in einer async-Methode die Überprüfung der inneren Ausnahmen von <xref:System.AggregateException>. Lokale Funktionen ermöglichen einen schnellen Abbruch Ihres Codes. Ihre Ausnahme kann sowohl synchron ausgelöst als auch beobachtet werden.

Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `GetMultipleAsync` verwendet, um für eine bestimmte Anzahl von Sekunden anzuhalten und ein zufälliges Vielfaches dieser Sekundenanzahl zurückzugeben. Die maximale Verzögerung beträgt 5 Sekunden. <xref:System.ArgumentOutOfRangeException> wird ausgegeben, wenn der Wert größer als 5 ist. Im folgenden Beispiel wird verdeutlicht, dass die Ausnahme, die bei der Übergabe eines Werts größer als 6 an die Methode `GetMultipleAsync` ausgelöst wird, von <xref:System.AggregateException> umschlossen wird, sobald die Methode `GetMultipleAsync` ausgeführt wird.

[!code-cs[LokaleFunktionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)] 

Wie beim Methodeniterator kann der Code aus diesem Beispiel umgestaltet werden, um die Validierung vor Aufruf der asynchronen Methode durchzuführen. Die Ausgabe des folgenden Beispiels zeigt, dass <xref:System.ArgumentOutOfRangeException> nicht von einer <x:System.AggregateException> umschlossen wird.

[!code-cs[LokaleFunktionAsync`](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)] 

## <a name="see-also"></a>Siehe auch
[Methoden](methods.md)

