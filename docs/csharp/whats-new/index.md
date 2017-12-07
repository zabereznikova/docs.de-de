---
title: "Neues in C# – Leitfaden für C#"
description: Wie sich die C#-Programmiersprache weiterentwickelt
keywords: C#, neueste Funktionen, Neues, Roslyn
author: BillWagner
ms.author: wiwagn
ms.date: 11/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 719fbe826b0b115b19067dbaf0d04f14e6534890
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-in-c"></a>Neues in C# #

Diese Seite enthält eine Roadmap zu den neuen Funktionen in jeder Hauptversion der C#-Sprache. Die folgenden Links bieten ausführliche Informationen zu den wichtigsten Funktionen, die in jedem Release hinzugefügt wurden.

> [!IMPORTANT]
> Für einige der Funktionen ist die C#-Sprache von Typen und Methoden in einer *Standardbibliothek* abhängig. Ein Beispiel ist die Ausnahmeverarbeitung. Alle `throw`-Anweisungen oder -Ausdrücke werden überprüft, um sicherzustellen, dass das ausgelöste Objekt von <xref:System.Exception> abgeleitet ist. Auf ähnliche Weise wird jedes `catch` überprüft, um sicherzustellen, dass der abgefangen Typ von <xref:System.Exception> abgeleitet ist. Jede Version kann neue Anforderungen hinzufügen. Um die neuesten Sprachfunktionen in älteren Umgebungen verwenden zu können, müssen Sie vielleicht bestimmte Bibliotheken installieren. Diese Abhängigkeiten werden auf der jeweiligen Seite für eine spezifische Version dokumentiert. Sie können mehr über die [Beziehungen zwischen Sprache und Bibliothek](relationships-between-language-and-library.md) erfahren, um Hintergrundinformationen zu dieser Abhängigkeit zu erhalten. 


* [C# 7.2](csharp-7-2.md):
    - Auf dieser Seite werden die neuesten Funktionen der Programmiersprache C# vorgestellt. C# 7.2 steht aktuell in [Visual Studio 2017 Version 15.5](https://www.visualstudio.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) zur Verfügung.

* [C# 7.1](csharp-7-1.md):
    - Auf dieser Seite werden die Features vorgestellt, die in C# 7.1 hinzugefügt wurden. Diese Features wurden in [Visual Studio 2017 version 15.3](https://www.visualstudio.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) hinzugefügt.

* [C# 7](csharp-7.md):
    - Auf dieser Seite werden die Funktionen vorgestellt, die in C# 7 hinzugefügt wurden. Diese Features wurden in [Visual Studio 2017](https://www.visualstudio.com/vs/whatsnew/) und in [.NET Core 1.0](../../core/whats-new/index.md) und höher hinzugefügt.
     
* [C# 6](csharp-6.md):
    - Auf dieser Seite werden die Funktionen vorgestellt, die in C# 6 eingefügt wurden. Diese Funktionen stehen für Windows-Entwickler in Visual Studio 2015 zur Verfügung; Entwickler, die C# unter macOS und Linux verwenden, können dazu .NET Core 1.0 nutzen.

<!--* [C# Interactive](../interactive/index.md): 
    - This page describes C# Interactive, an interactive Read Eval Print Loop (REPL) that you can use to explore the C# language. You can use it to write code interactively and see it execute immediately, without any compile or build step.
-->
* [Plattformübergreifender Support](../../core/index.md):
    - C# kann aufgrund des .NET Core Supports auf mehreren Plattformen ausgeführt werden. Wenn Sie C# unter macOS oder unter einer der vielen unterstützten Linux-Distributionen ausprobieren möchten, informieren Sie sich über .NET Core.

<!--
- [.NET Compiler Platform SDK](../roslyn/index.md):
    - The .NET Compiler Platform SDK enables you to write code that performs static analysis on C# code. You can use these APIs to find potential errors, or bad practices, suggest fixes, and even implement those fixes.
-->
  
## <a name="previous-versions"></a>Frühere Versionen
Im Folgenden sind die Hauptfunktionen aufgelistet, die mit vorherigen Versionen von C# und Visual Studio .NET eingeführt wurden.  
  
 * Visual Studio .NET 2013: 
     - Diese Version von Visual Studio enthielt Fehlerkorrekturen, Leistungsoptimierungen und eine Technologievorschau von .NET Compiler Platform („Roslyn“), die zum <!--Link to ../roslyn/index.md-->.NET Compiler Platform SDK wurde.

 * C# 5, Visual Studio .NET 2012: 
     - `Async` / `await` und [Aufruferinformationsattribute](../programming-guide/concepts/caller-information.md).

 * C# 4, Visual Studio .NET 2010: 
     - `Dynamic`, [benannte Argumente](../programming-guide/classes-and-structs/named-and-optional-arguments.md), optionale Parameter, generische [Ko-/Kontravarianz](../programming-guide/concepts/covariance-contravariance/index.md).

 * C# 3, Visual Studio .NET 2008: 
     - Objekt- und Auflistungsinitialisierer, Lambdaausdrücke, Erweiterungsmethoden, anonyme Typen, automatische Eigenschaften, lokaler `var`-Typrückschluss und [Language Integrated Query (LINQ)](../programming-guide/concepts/linq/index.md).

 * C# 2, Visual Studio .NET 2005: 
     - Anonyme Methoden, generische Typen, auf NULL festlegbare Typen, Iteratoren/Yield, `static`-Klassen und Ko-/Kontravarianz für Delegaten.

 * C# 1.1, Visual Studio .NET 2003: 
     - `#line`-Pragma und XML-Dokumentationskommentare

 * C# 1, Visual Studio .NET 2002: 
     - Die erste Version von [C#](../csharp.md).   
