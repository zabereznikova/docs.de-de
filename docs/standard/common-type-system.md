---
title: Allgemeines Typsystem und Common Language Specification
description: Erfahren Sie, wie das allgemeine Typsystem (CTS) und die Common Language Specification (CLS) die .NET-Unterstützung mehrerer Sprachen ermöglichen.
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.openlocfilehash: 8983e456b051ace434fda9f6ed9cf9028c2ec2d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187679"
---
# <a name="common-type-system--common-language-specification"></a>Allgemeines Typsystem und Common Language Specification

Diese im Kontext von .NET frei verwendeten Begriffe sind dennoch entscheidend für das Verständnis wie eine .NET-Implementierung die mehrsprachige Entwicklung ermöglicht, und wie diese Entwicklung erfolgt.

## <a name="common-type-system"></a>Allgemeines Typsystem

Beachten Sie zunächst, dass eine .NET-Implementierung _sprachunabhängig_ ist. Das bedeutet nicht nur, dass ein Programmierer Code in jeder Sprache schreiben kann, die in IL kompiliert werden kann. Es bedeutet auch, dass dieser in der Lage sein muss, mit Code zu interagieren, der in anderen Sprachen geschrieben ist, die in einer .NET-Implementierung verwendet werden können.

Damit dies transparent erfolgen kann, ist eine allgemeine Methode zur Beschreibung aller unterstützten Typen erforderlich. Hierzu dient das allgemeine Typsystem (Common Type System, CTS). Es ist für verschiedene Zwecke bestimmt:

* Einrichten eines Frameworks für die sprachübergreifende Ausführung.
* Bereitstellen eines objektorientierten Modells zur Unterstützung der Implementierung verschiedener Sprachen in einer .NET-Implementierung.
* Definieren eines Satzes von Regeln, die alle Programmiersprachen bei der Arbeit mit Typen einhalten müssen.
* Bereitstellen einer Bibliothek, die die bei der Anwendungsentwicklung verwendeten grundlegenden primitiven Datentypen enthält (z.B. `Boolean`, `Byte`, `Char` usw.)

CTS definiert zwei Hauptarten von Typen, die unterstützt werden sollten: Verweis- und Werttypen. Ihre Namen weisen auf ihre Definitionen.

Verweistypenobjekte werden durch einen Verweis auf den tatsächlichen Wert des Objekts dargestellt. Ein Verweis entspricht hier einem Zeiger in C/C++. Dieser verweist einfach auf einen Speicherbereich, in dem sich die Werte der Objekte befinden. Dies hat einen tiefgreifenden Einfluss auf die Art der Verwendung dieser Typen. Wenn Sie einen Verweistyp einer Variablen zuweisen und dann z.B. die Variable einer Methode übergeben, werden Änderungen des Objekts im Hauptobjekt berücksichtigt; es findet kein Kopiervorgang statt.

Werttypen sind das Gegenteil, wobei die Objekte durch ihre Werte dargestellt werden. Wenn Sie einer Variablen einen Werttyp zuweisen, kopieren Sie im Grunde einen Wert des Objekts.

CTS definiert verschiedene Kategorien von Typen, jeweils mit ihrer spezifischen Semantik und Nutzung:

* Klassen
* Strukturen
* Enumerationen
* Schnittstellen
* Delegaten

CTS definiert auch alle anderen Eigenschaften der Typen, z.B. Zugriffsmodifizierer, welche Typmember gültig sind, wie Vererbung und Überladung funktionieren usw. Leider ist es nicht möglich, in einem Einführungsartikel wie diesem einen dieser Aspekte ausführlich zu behandeln, aber Sie finden im Abschnitt [Weitere Ressourcen](#more-resources) am Ende Links zu ausführlicheren Dokumenten, die diese Themen behandeln.

## <a name="common-language-specification"></a>Common Language Specification

Um vollständige Interoperabilitätsszenarien zu aktivieren, müssen alle Objekte, die im Code erstellt werden, sich auf eine gewisse Gemeinsamkeit in den Sprachen verlassen, von denen sie verwendet werden (die ihre _Aufrufer_ sind). Da es zahlreiche verschiedene Sprachen gibt, legt .NET diese Gemeinsamkeiten in der sogenannten **Common Language Specification** (CLS) fest. Die CLS definiert einen Satz von Funktionen, die viele gängige Anwendungen benötigen. Darüber hinaus bietet sie für jede Sprache, die in .NET implementiert wird, Anweisungen, was diese unterstützen muss.

Die CLS ist eine Teilmenge des CTS. Dies bedeutet, dass alle Regeln im CTS auch für die CLS gelten, es sei denn, die CLS-Regeln sind strikter. Wenn eine Komponente nur gemäß der Regeln in der CLS erstellt wird, d.h., nur die CLS-Funktionen werden in der API verfügbar gemacht, gilt sie als **CLS-kompatibel**. Die `<framework-librares>` sind z.B. genau deshalb CLS-kompatibel, weil sie in allen von .NET unterstützten Sprachen übergreifend funktionieren müssen.

Die im Abschnitt [Weitere Ressourcen](#more-resources) unten aufgelisteten Dokumente bieten Ihnen eine Übersicht über alle in der CLS enthaltenen Funktionen.

## <a name="more-resources"></a>Weitere Ressourcen

* [Allgemeines Typsystem](./base-types/common-type-system.md)
* [Common Language Specification](language-independence-and-language-independent-components.md)
