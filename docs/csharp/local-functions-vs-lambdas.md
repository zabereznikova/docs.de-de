---
title: "Lokale Funktionen im Vergleich zu Lambdaausdrücken"
description: "Erfahren Sie, warum lokale Funktionen unter Umständen besser geeignet sind als Lambdaausdrücke."
keywords: "C#, .NET, .NET Core, neueste Funktionen, Neuigkeiten, lokale Funktionen, Lambdaausdrücke"
author: BillWagner
ms.author: wiwagn
ms.date: 06/27/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
ms.translationtype: HT
ms.sourcegitcommit: 4582cb0ee091526423cce3fc1d8243029f34f59c
ms.openlocfilehash: 366d7465433f2786960e22418b8aa46ba10e1fd1
ms.contentlocale: de-de
ms.lasthandoff: 08/16/2017

---
# <a name="local-functions-compared-to-lambda-expressions"></a>Lokale Funktionen im Vergleich zu Lambdaausdrücken

Auf den ersten Blick sind [lokale Funktionen](programming-guide/classes-and-structs/local-functions.md) und [Lambdaausdrücke](lambda-expressions.md) sehr ähnlich.
Je nach Ihren Anforderungen sind lokale Funktionen möglicherweise aber eine viel bessere und einfachere Lösung.

Sehen wir uns die Unterschiede zwischen der Implementierungen des Fakultätsalgorithmus als lokale Funktion und als Lambdaausdruck an. Erste die Version mit einer lokalen Funktion:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Rekursive Fakultät mit lokaler Funktion")]

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Rekursive Fakultät mit Lambdaausdrücken")]

Zuerst werden Lambdaausdrücke durch das Instanziieren und Abrufen eines Delegats implementiert. Lokale Funktionen werden als Methodenaufrufe implementiert.
Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann.
Lokale Funktionen erfordern diesen Mehraufwand nicht. Im obigen Beispiel hat die Version mit der lokalen Funktion zwei Zuordnungen weniger als die Version mit dem Lambdaausdruck.

Diese rekursive Methode ist einfach genug, dass die lokale Funktion als private Methode mit einem vom Compiler generierten Namen implementiert wird. Der einzige Unterschied zu anderen privaten Methoden ist, dass sie semantisch innerhalb der äußeren Funktion begrenzt ist.

Zweitens können lokale Funktionen aufgerufen werden, bevor sie definiert werden. Lambdaausdrücke müssen deklariert werden, bevor sie definiert werden. Dies bedeutet, dass lokale Funktionen wie oben dargestellt einfacher in rekursiven Algorithmen verwendet werden.

Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.
Rekursiver Algorithmen sind einfacher mit lokalen Funktion zu erstellen.

Drittens muss der Compiler für Lambdaausdrücke zunächst immer eine anonyme Klasse und eine Instanz dieser Klasse erstellen, um alle Variablen zu speichern, die vom Abschluss erfasst wurden. Betrachten Sie das folgende asynchrone Beispiel:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Methode mit Lambdaausdruck, die Aufgabe zurückgibt")]

Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. Im Fall von lokalen Funktionen ist das Objekt, das den Abschluss implementiert, möglicherweise vom Typ `struct`. Dadurch würde bei einer Zuweisung gespart.

> [!NOTE]
> Die Entsprechung dieser Methode mit der lokalen Funktion verwendet auch eine Klasse für den Abschluss. Ob der Abschluss für eine lokale Funktion als `class` oder `struct` implementiert wird, ist ein Implementierungsdetail. Eine lokale Funktion verwendet möglicherweise `struct`, während ein Lambdaausdruck immer `class` nutzt.

[!code-csharp[TaskLocalFunctionExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#29_TaskExample "Aufgabenrückgabemethode mit lokaler Funktion ")]

Eine letzter Vorteil, der in diesem Beispiel zu kurz gekommen ist, besteht darin, dass lokale Funktionen mithilfe der `yield return`-Syntax als Iteratoren implementiert werden können, um eine Sequenz von Werten zu erzeugen.

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen.
Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.

