---
title: 'Erste Schritte: Einführung in die Programmiersprache C# und in .NET'
description: Lernen Sie die Grundlagen von C# und .NET kennen. Verschaffen Sie sich einen Überblick über die Programmiersprache C# und das .NET-Ökosystem.
ms.date: 10/13/2020
ms.openlocfilehash: 94d49be28fbdba8f58ca16e959a10643d6467c63
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160957"
---
# <a name="introduction-to-the-c-language-and-net"></a>Einführung in die Programmiersprache C# und in .NET

C# ist eine elegante und typsichere objektorientierte Programmiersprache. C# ermöglicht Entwicklern das Erstellen zahlreicher sicherer und robuster Anwendungen, die im .NET-Ökosystem ausgeführt werden.

## <a name="c-language"></a>C#-Sprache

Die C#-Syntax ist trotz ihrer Ausdrucksfülle einfach und leicht zu erlernen. Die C#-Syntax mit geschweiften Klammern ist für alle Benutzer sofort erkennbar, die mit C, C++, Java oder JavaScript vertraut sind. Entwickler, die mit einer dieser Sprachen vertraut sind, können in C# normalerweise innerhalb kürzester Zeit arbeiten. C# bietet leistungsstarke Features wie z. B. Typen, Delegaten, Lambdaausdrücke, Musterabgleich und sicheren direkten Speicherzugriff. C# unterstützt generische Methoden und Typen, die eine bessere Typsicherheit und Leistung bieten. C# stellt Iteratoren bereit, mit denen Implementierer von Auflistungsklassen benutzerdefinierte Verhaltensweisen für Clientcode definieren können. LINQ-Ausdrücke (Language Integrated Query) machen eine Abfrage mit starker Typisierung zu einem erstklassigen Sprachkonstrukt.

Als objektorientierte Sprache unterstützt C# die Konzepte der Kapselung, Vererbung und Polymorphie. Eine Klasse kann direkt von einer übergeordneten Klasse erben, aber auch eine beliebige Anzahl von Schnittstellen implementieren. Methoden, die virtuelle Methoden in einer übergeordneten Klasse überschreiben, erfordern das `override`-Schlüsselwort als Möglichkeit, eine versehentliche Neudefinition zu verhindern. In C# verhält sich eine Struktur wie eine vereinfachte Klasse. Sie entspricht einem auf dem Stapel reservierten Typ, der Schnittstellen implementieren kann, jedoch keine Vererbung unterstützt. C# stellt auch Datensätze bereit, bei denen es sich um Klassentypen handelt, deren Zweck es ist, Datenwerte zu speichern.

C# vereinfacht die Entwicklung von Softwarekomponenten mithilfe mehrerer innovativer Sprachkonstrukte, einschließlich der folgenden:

- Gekapselte Methodensignaturen, *Delegaten* genannt, die typsichere Ereignisbenachrichtigungen ermöglichen.
- Eigenschaften, die als Zugriffsmethoden für private Membervariablen dienen.
- Attribute, die zur Laufzeit deklarative Metadaten zu Typen bereitstellen.
- Inline-XML-Dokumentationskommentare.
- LINQ (Language Integrated Query), die integrierte Abfragefunktionen für eine Vielzahl von Datenquellen bereitstellt
- Musterabgleich, der die Ablaufsteuerung durch Überprüfen von Datentypen und Werten ermöglicht

Sie interagieren mit nativen Komponenten über einen Prozess namens „Interop“. Mithilfe von Interop bieten C#-Programme dieselbe Funktionalität wie systemeigene C++-Anwendungen. C# unterstützt sogar Zeiger und das Konzept des „unsicheren“ Codes für jene Fälle, in denen direkter Speicherzugriff wichtig ist.

Der C#-Erstellungsprozess ist im Vergleich zu C und C++ einfach und flexibler als in Java. Es gibt keine separaten Headerdateien. Außerdem ist es nicht erforderlich, Methoden und Typen in einem bestimmten Ordner zu deklarieren. Eine C#-Quelldatei kann eine beliebige Anzahl von Klassen, Strukturen, Schnittstellen und Ereignissen definieren.

Die folgenden zusätzlichen C#-Ressourcen stehen zur Verfügung:

- Eine gute allgemeine Einführung in die Sprache finden Sie im [Überblick über C#](../tour-of-csharp/index.md).
- Ausführliche Informationen zu bestimmten Aspekte der Programmiersprache C# finden Sie in der [C#-Referenz](../language-reference/index.md).
- Weitere Informationen zu LINQ finden Sie unter [LINQ (Language-Integrated Query)](../programming-guide/concepts/linq/index.md).

## <a name="net-platform-architecture"></a>.NET-Plattformarchitektur

C#-Programme werden auf Grundlage von .NET ausgeführt, ein virtuelles Ausführungssystem namens Common Language Runtime (CLR) sowie einheitliche Klassenbibliotheken. Die CLR ist die kommerzielle Implementierung der Common Language Infrastructure (CLI) von Microsoft, ein internationaler Standard. Die CLI ist die Grundlage für das Erstellen von Ausführungs- und Entwicklungsumgebungen, in denen Sprachen und Bibliotheken nahtlos zusammenarbeiten.

Der in C# geschriebene Quellcode wird in eine [Zwischensprache](../../standard/managed-code.md) kompiliert, die konform mit der CLI-Spezifikation ist. Der IL-Code wird zusammen mit Ressourcen wie z. B. Bitmaps und Zeichenfolgen in einer Assembly gespeichert, die normalerweise die Erweiterung DLL aufweist. Eine Assembly enthält ein Manifest, das Informationen über die Typen, die Version und die Kultur der Assembly bereitstellt.

Wenn das C#-Programm ausgeführt wird, wird die Assembly in die CLR geladen. Die CLR konvertiert den IL-Code mithilfe der JIT-Kompilierung (Just-In-Time) in native Computeranweisungen. Die CLR stellt weitere Dienste zur automatischen Garbage Collection, Ausnahmebehandlung und Ressourcenverwaltung bereit. Der über die CLR ausgeführte Code wird manchmal als „verwalteter Code“ bezeichnet. Dieser steht im Gegensatz zum „nicht verwalteten Code“, der in native Maschinensprache kompiliert wird, die auf ein bestimmtes System abgestimmt ist.

Eines der wichtigsten Features in .NET ist die Sprachinteroperabilität. Der vom C#-Compiler erzeugte IL-Code entspricht dem allgemeinen Typsystem (CTS, Common Type Specification). Der über C# generierte IL-Code kann mit Code interagieren, der über die .NET-Versionen von F#, Visual Basic, C++ oder einer der mehr als 20 anderen CTS-konformen Sprachen generiert wurde. Eine einzelne Assembly kann mehrere in verschiedenen .NET-Sprachen erstellte Module enthalten, und die Typen können aufeinander verweisen, als wären sie in derselben Sprache geschrieben worden.

Zusätzlich zu den Laufzeitdiensten enthält .NET auch umfangreiche Bibliotheken. Diese Bibliotheken unterstützen viele verschieden Workloads. Diese sind in Namespaces organisiert,die eine Vielzahl hilfreicher Funktionen bereitstellen: von der Dateieingabe und -ausgabe über die Zeichenfolgenbearbeitung bis hin zur XML-Analyse und zu Webanwendungsframeworks und Windows Forms-Steuerelementen. Eine typische C#-Anwendung verwendet für die Ausführung von Routinevorgängen ausgiebig die .NET-Klassenbibliothek.

Weitere Informationen zu .NET finden Sie in der [Übersicht über .NET](../../core/introduction.md).
