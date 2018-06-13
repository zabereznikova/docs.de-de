---
title: C#-Strukturen – Überblick über C#
description: Lernen Sie die Grundlagen der als Strukturen bezeichneten C#-Werttypen kennen.
ms.date: 08/10/2016
ms.assetid: 88a74571-f741-4a31-a2b5-1ccf165535b8
ms.openlocfilehash: dac0952e6a55a16ecefec79f9789f9e2d44aada1
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058959"
---
# <a name="structs"></a>Strukturen

Wie Klassen sind ***Strukturen*** Datenstrukturen, die Datenmember und Funktionsmember enthalten können, aber im Gegensatz zu Klassen sind Strukturen Werttypen und erfordern keine Heapzuordnung. Eine Variable eines Strukturtyps speichert die Daten der Struktur direkt, während eine Variable eines Klassentyps einen Verweis auf ein dynamisch zugeordnetes Objekt speichert. Strukturtypen unterstützen keine benutzerdefinierte Vererbung, und alle Strukturtypen erben implizit vom Typ <xref:System.ValueType>, der wiederum implizit von `object` erbt.

Strukturen sind besonders nützlich für kleine Datenstrukturen, die über Wertsemantik verfügen. Komplexe Zahlen, Punkte in einem Koordinatensystem oder Schlüssel-Wert-Paare im Wörterbuch sind gute Beispiele für Strukturen. Die Verwendung von Strukturen statt Klassen für kleine Datenstrukturen kann bei der Anzahl der Speicherbelegungen, die eine Anwendung durchführt, einen großen Unterschied ausmachen. Das folgende Programm erstellt und initialisiert z.B. ein Array aus 100 Punkten. Mit `Point` als implementierter Klasse werden 101 separate Objekte instanziiert – eines für das Array und jeweils eines für jedes der 100 Elemente.

[!code-csharp[PointClassUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L5-L13)]

Eine Alternative ist, „Point“ zu einer Struktur zu machen.

[!code-csharp[PointStruct](../../../samples/snippets/csharp/tour/structs/Point.cs#L3-L11)]

Jetzt wird nur ein Objekt instanziiert – für das Array – und die `Point`-Instanzen werden inline im Array gespeichert.

Strukturkonstruktoren werden mit dem neuen Operator `new` aufgerufen, doch das bedeutet nicht, dass der Arbeitsspeicher belegt wird. Statt ein Objekt dynamisch zuzuordnen und einen Verweis darauf zurückzugeben, gibt ein Strukturkonstruktor einfach den Strukturwert selbst zurück (in der Regel in einen temporären Speicherort auf dem Stapel), und dieser Wert wird dann nach Bedarf kopiert.

Mit Klassen können zwei Variablen auf das gleiche Objekt verweisen, und so können an einer Variablen durchgeführte Vorgänge das Objekt beeinflussen, auf das die andere Variable verweist. Mit Strukturen besitzt jede Variable eine eigene Kopie der Daten, und es ist nicht möglich, dass an einer Variablen durchgeführte Vorgänge die andere beeinflussen. Welche Ausgabe das folgende Codefragment erzeugt, hängt beispielsweise davon ab, ob „Point“ eine Klasse oder eine Struktur ist.

[!code-csharp[PointUse](../../../samples/snippets/csharp/tour/structs/Program.cs#L19-L22)]

Wenn `Point` eine Klasse ist, ist die Ausgabe 20, da „a“ und „b“ auf das gleiche Objekt verweisen. Wenn „Point“ eine Struktur ist, ist die Ausgabe 10, da die Zuweisung von `a` zu `b` eine Kopie des Werts erstellt, und diese Kopie ist nicht von der nachfolgenden Zuweisung zu `a.x` betroffen.

Im vorherigen Beispiel werden zwei der Einschränkungen von Strukturen hervorgehoben. Erstens ist das Kopieren einer gesamten Struktur in der Regel weniger effizient als das Kopieren eines Objektverweises, sodass Zuweisung und Wertparameterübergabe mit Strukturen aufwändiger sein kann als mit Verweistypen. Zweitens ist es mit Ausnahme der `in`-, `ref`- und `out`-Parameter nicht möglich, Verweise auf Strukturen zu erstellen, was ihre Verwendung in einer Reihe von Situationen ausschließt.

>[!div class="step-by-step"]
[Zurück](classes-and-objects.md)
[Weiter](arrays.md)
