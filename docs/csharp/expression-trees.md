---
title: Ausdrucksbaumstrukturen
description: Weitere Informationen zu Ausdrucksbaumstrukturen in .NET Core und wie sie verwendet werden, um Code als Strukturen darzustellen, die Sie überprüfen, ändern und ausführen können.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: aceb4719-0d5a-4b19-b01f-b51063bcc54f
ms.openlocfilehash: 62f5b93097ee8ad2177fc0bb484c656408f91f30
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062508"
---
# <a name="expression-trees"></a>Ausdrucksbaumstrukturen

Wenn Sie LINQ verwendet haben, verfügen Sie über Erfahrung mit einer umfangreichen Bibliothek, in der die `Func`-Typen Teil des API-Satzes sind. (Wenn Sie nicht mit LINQ vertraut sind, möchten Sie möglicherweise vorher [das LINQ-Tutorial](linq/index.md) und den Artikel zu [lambda expressions (Lambdaausdrücke)](language-reference/operators/lambda-expressions.md) lesen.) *Ausdrucksbaumstrukturen* bieten eine umfangreichere Interaktion mit den Argumenten, die Funktionen sind.

Sie schreiben die Argumente der Funktion in der Regel mithilfe von Lambdaausdrücken, wenn Sie LINQ-Abfragen erstellen. In einer normalen LINQ-Abfrage werden die Funktionsargumente in einen Delegaten transformiert, den der Compiler erstellt.

Wenn Sie eine umfangreichere Interaktion haben möchten, müssen Sie *Ausdrucksbaumstrukturen* verwenden.
Ausdrucksbaumstrukturen stellen Code wie eine Struktur dar, die Sie untersuchen, ändern oder ausführen können. Diese Tools bieten Ihnen die Möglichkeit, Code während der Laufzeit zu ändern. Sie können Code schreiben, der ausgeführte Algorithmen untersucht oder neue Funktionen einfügt. In erweiterten Szenarios können Sie ausgeführte Algorithmen ändern und sogar C#-Ausdrücke für die Ausführung in einer anderen Umgebung in eine andere Form übersetzen.

Sie haben wahrscheinlich bereits Code geschrieben, der Ausdrucksbaumstrukturen verwendet. LINQ-APIs von Entity Framework akzeptieren Ausdrucksbaumstrukturen als Argumente für das LINQ-Abfrageausdrucksmuster.
So kann [Entity Framework](/ef/) die Abfrage übersetzen, die Sie in C# in SQL geschrieben haben, die in der Datenbank-Engine ausgeführt wird. Ein weiteres Beispiel ist [Moq](https://github.com/Moq/moq), was ein beliebtes Mockingframework für .NET ist.

In den verbleibenden Abschnitten dieses Tutorials wird untersucht, was Ausdrucksbaumstrukturen sind, es werden die Framework-Klassen untersucht, die Ausdrucksbaumstrukturen unterstützen, und es wird gezeigt, wie Sie mit Ausdrucksbaumstrukturen arbeiten. Sie erfahren, wie Sie Ausdrucksbaumstrukturen lesen und diese erstellen, wie Sie geänderte Ausdrucksbaumstrukturen erstellen und wie Sie Code von dargestellten Ausdrucksbaumstrukturen ausführen. Nach dem Lesen können Sie mit diesen Strukturen umfangreiche adaptive Algorithmen erstellen.

1. [Ausdrucksbaumstrukturen mit Erläuterung](expression-trees-explained.md)

    Verstehen der Struktur und der Konzepte hinter *Ausdrucksbaumstrukturen*.

2. [Framework-Typen, die Ausdrucksbaumstrukturen unterstützen](expression-classes.md)

    Erfahren Sie mehr über die Strukturen und Klassen, die Ausdrucksbaumstrukturen definieren und bearbeiten.

3. [Ausführen von Ausdrücken](expression-trees-execution.md)

    Erfahren Sie, wie Sie eine Ausdrucksbaumstruktur, die als Lambdaausdruck dargestellt wird, in einen Delegaten konvertieren, und wie Sie den resultierenden Delegaten ausführen.

4. [Interpretieren von Ausdrücken](expression-trees-interpreting.md)

    Erfahren Sie, wie Sie *Ausdrucksbaumstrukturen* durchlaufen und untersuchen, um zu verstehen, welchen Code die Ausdrucksbaumstruktur darstellt.

5. [Erstellen von Ausdrücken](expression-trees-building.md)

    Erfahren Sie, wie Sie die Knoten für eine Ausdrucksbaumstruktur erstellen, und wie Sie Ausdrucksbaumstrukturen erstellen.

6. [Übersetzen von Ausdrücken](expression-trees-translating.md)

    Erfahren Sie, wie Sie eine geänderte Kopie einer Ausdrucksbaumstruktur erstellen oder wie Sie eine Ausdrucksbaumstruktur in ein anderes Format übersetzen.

7. [Schlussbemerkung](expression-trees-summary.md)

    Überprüfen Sie die Informationen zu Ausdrucksbaumstrukturen.
