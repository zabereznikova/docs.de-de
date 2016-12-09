---
title: Allgemeines Typsystem und Common Language Specification
description: Allgemeines Typsystem und Common Language Specification
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
translationtype: Human Translation
ms.sourcegitcommit: 9cf6022fc910bc5418c03c0fa81d9432d85be3b0
ms.openlocfilehash: f655c141a0c86da7905091c138b7ec4324cad07a

---

# <a name="common-type-system-common-language-specification"></a>Allgemeines Typsystem und Common Language Specification

Diese in der .NET-Welt frei verwendeten Begriffe sind wirklich entscheidend für das Verständnis der Art und Weise, in der die .NET-Plattform mehrsprachige Entwicklung ermöglicht, und der Funktionsweise.

## <a name="common-type-system"></a>Allgemeines Typsystem

Um von vorn zu beginnen, beachten Sie, dass die .NET-Plattform _sprachunabhängig_ ist. Dies bedeutet nicht nur, dass ein Programmierer Code in jeder Sprache schreiben kann, die in IL kompiliert werden kann. Dies bedeutet auch, dass er in der Lage sein muss, mit Code zu interagieren, der in anderen Sprachen geschrieben ist, die auf der .NET-Plattform verwendet werden können.

Damit dies transparent erfolgen kann, ist eine allgemeine Methode zur Beschreibung aller unterstützten Typen erforderlich. Hierzu dient das allgemeine Typsystem (Common Type System, CTS). Es ist für verschiedene Zwecke bestimmt:

*   Einrichten eines Frameworks für die sprachübergreifende Ausführung.
*   Bereitstellen eines objektorientierten Modells zur Unterstützung der Implementierung verschiedener Sprachen auf der .NET-Plattform.
*   Definieren eines Satzes von Regeln, die alle Programmiersprachen bei der Arbeit mit Typen einhalten müssen.
*   Bereitstellen einer Bibliothek, die die bei der Anwendungsentwicklung verwendeten grundlegenden primitiven Datentypen enthält (z.B. `Boolean`, `Byte`, `Char` etc.).

CTS definiert zwei Hauptarten von Typen, die unterstützt werden sollten: Verweis- und Werttypen. Ihre Namen weisen auf ihre Definitionen.

Verweistypenobjekte werden durch einen Verweis auf den tatsächlichen Wert des Objekts dargestellt; ein Verweis entspricht hier einem Zeiger in C/C++. Er verweist einfach auf einen Speicherbereich, in dem sich die Werte der Objekte befinden. Dies hat einen tiefgreifenden Einfluss auf die Art der Verwendung dieser Typen. Wenn Sie einen Verweistyp einer Variablen zuweisen und dann z.B. die Variable einer Methode übergeben, werden Änderungen des Objekts im Hauptobjekt berücksichtigt; es findet kein Kopiervorgang statt.

Werttypen sind das Gegenteil, wobei die Objekte durch ihre Werte dargestellt werden. Wenn Sie einer Variablen einen Werttyp zuweisen, kopieren Sie im Grunde einen Wert des Objekts.

CTS definiert verschiedene Kategorien von Typen, jeweils mit ihrer spezifischen Semantik und Nutzung:

*   Klassen
*   Strukturen
*   Enumerationen
*   Schnittstellen
*   Delegaten

CTS definiert auch alle anderen Eigenschaften der Typen, z.B. Zugriffsmodifizierer, welche Typmember gültig sind, wie Vererbung und Überladung funktionieren usw. Leider ist es nicht möglich, in einem Einführungsartikel wie diesem einen dieser Aspekte ausführlich zu behandeln, aber Sie finden im Abschnitt [Weitere Ressourcen](#more-resources) am Ende Links zu ausführlicheren Dokumenten, die diese Themen behandeln.

## <a name="common-language-specification"></a>Common Language Specification

Um vollständige Interoperabilitätsszenarien zu aktivieren, müssen alle Objekte, die im Code erstellt werden, sich auf eine gewisse Gemeinsamkeit in den Sprachen verlassen, von denen sie verwendet werden (die ihre _Aufrufer_ sind). Da es zahlreiche verschiedene Sprachen gibt, sind diese Gemeinsamkeiten für die .NET-Plattform in der so genannten **Common Language Specification** (CLS) festgelegt. Die CLS definiert einen Satz von Funktionen, die viele gängige Anwendungen benötigen. Darüber hinaus bietet sie für jede Sprache eine Art Rezept über das, was sie unterstützen muss. Dies ist über der .NET-Plattform implementiert.

Die CLS ist eine Teilmenge des CTS. Dies bedeutet, dass alle Regeln im CTS auch für die CLS gelten, es sei denn, die CLS-Regeln sind strikter. Wenn eine Komponente nur gemäß der Regeln in der CLS erstellt wird, d.h., nur die CLS-Funktionen werden in der API verfügbar gemacht, gilt sie als **CLS-kompatibel**. Die `<framework-librares>` sind z.B. genau deshalb CLS-kompatibel, weil sie in allen von der .NET-Plattform unterstützten Sprachen übergreifend funktionieren müssen.

Die im Abschnitt [Weitere Ressourcen](#more-resources) unten aufgelisteten Dokumente bieten Ihnen eine Übersicht über alle in der CLS enthaltenen Funktionen.

## <a name="more-resources"></a>Weitere Ressourcen

*   [Allgemeines Typsystem](https://msdn.microsoft.com/library/zcx1eb1e.aspx)
*   [Common Language Specification](https://msdn.microsoft.com/library/12a7a7h3.aspx)



<!--HONumber=Nov16_HO3-->


