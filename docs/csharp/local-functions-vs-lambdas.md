---
title: "Lokale Funktionen im Vergleich zu Lambdaausdrücken"
description: "Warum lokale Funktionen besser geeignet als Lambdaausdrücke sein können"
keywords: "C#, .NET, .NET Core, neueste Funktionen, Neuigkeiten, lokale Funktionen, Lambdaausdrücke"
author: BillWagner
ms.author: wiwagn
ms.date: 10/27/2016
ms.topic: article
ms.prod: visual-studio-dev-15
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 368d1752-3659-489a-97b4-f15d87e49ae3
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bba2a8d183f928e298c452f6ec132f3eb9dffbd3
ms.lasthandoff: 03/13/2017

---

### <a name="local-functions-compared-to-lambda-expressions"></a>Lokale Funktionen im Vergleich zu Lambdaausdrücken

Sie können in manchen Anwendungsfällen einen Lambdaausdruck erstellen und ihn verwenden, ohne eine lokale Funktion erstellen zu müssen. Hier ist ein Beispiel für eine asynchrone Methode, die genau das macht:

[!code-csharp[TaskLambdaExample](../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Methode mit Lambdaausdruck, die Aufgabe zurückgibt")]

Es gibt jedoch eine Anzahl von Gründen, lokale Funktionen lieber zu verwenden, anstatt Lambdaausdrücke zu definieren und aufzurufen.

Für Lambdaausdrücke muss der Compiler zunächst eine anonyme Klasse und eine Instanz dieser Klasse erstellen, um alle Variablen zu speichern, die vom Abschluss erfasst wurden. Der Abschluss dieses Lambdaausdrucks enthält die Variablen `address`, `index` und `name`. 

Zweitens werden Lambdaausdrücke durch das Instanziieren und Abrufen eines Delegats implementiert. Lokale Funktionen werden als Methodenaufrufe implementiert.
Die für Lambdaausdrücke erforderliche Instanziierung bedeutet zusätzliche Speicherbelegung, was ein Leistungsfaktor in zeitkritischen Codepfaden sein kann.
Lokale Funktionen erfordern diesen Mehraufwand nicht.

Drittens können lokale Funktionen aufgerufen werden, bevor sie definiert werden. Lambdaausdrücke müssen deklariert werden, bevor sie definiert werden. Dies bedeutet, dass lokale Funktionen einfacher in rekursiven Algorithmen verwendet werden:

[!code-csharp[LocalFunctionFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Rekursive Fakultät mit lokaler Funktion")]

Vergleichen Sie diese Implementierung mit einer Version, die Lambdaausdrücke verwendet:

[!code-csharp[26_LambdaFactorial](../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Rekursive Fakultät mit Lambdaausdrücken")]

Beachten Sie, dass die Version mit Lambdaausdrücken den Lambdaausdruck `nthFactorial` deklarieren und initialisieren muss, bevor er definiert wird. Wird das nicht gemacht, führt dies zu einem Kompilierzeitfehler, weil auf `nthFactorial` verwiesen wurde, bevor es zugewiesen wurde.
Rekursiver Algorithmen sind einfacher mit lokalen Funktion zu erstellen. 

Während lokale Funktionen für Lambdaausdrücke als überflüssig erscheinen, dienen sie tatsächlich anderen Zwecken und haben unterschiedliche Verwendungen.
Lokale Funktionen sind effizienter, im Fall dass Sie eine Funktion schreiben möchten, die nur aus dem Kontext einer anderen Methode abgerufen wird.


