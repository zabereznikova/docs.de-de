---
title: Neues in C# – Leitfaden für C#
description: Wie sich die C#-Programmiersprache weiterentwickelt
ms.date: 11/13/2017
ms.assetid: 77deec51-a14d-46d4-9bb3-faf449477149
ms.openlocfilehash: 399550178a12ff520dff033f0f1dc4a7cdfb9591
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314671"
---
# <a name="whats-new-in-c"></a>Neues in C# #

Diese Seite enthält eine Roadmap zu den neuen Funktionen in jeder Hauptversion der C#-Sprache. Die folgenden Links bieten ausführliche Informationen zu den wichtigsten Funktionen, die in jedem Release hinzugefügt wurden.

> [!IMPORTANT]
> Für einige der Funktionen ist die C#-Sprache von Typen und Methoden in einer *Standardbibliothek* abhängig. Ein Beispiel ist die Ausnahmeverarbeitung. Alle `throw`-Anweisungen oder -Ausdrücke werden überprüft, um sicherzustellen, dass das ausgelöste Objekt von <xref:System.Exception> abgeleitet ist. Auf ähnliche Weise wird jedes `catch` überprüft, um sicherzustellen, dass der abgefangen Typ von <xref:System.Exception> abgeleitet ist. Jede Version kann neue Anforderungen hinzufügen. Um die neuesten Sprachfunktionen in älteren Umgebungen verwenden zu können, müssen Sie vielleicht bestimmte Bibliotheken installieren. Diese Abhängigkeiten werden auf der jeweiligen Seite für eine spezifische Version dokumentiert. Sie können mehr über die [Beziehungen zwischen Sprache und Bibliothek](relationships-between-language-and-library.md) erfahren, um Hintergrundinformationen zu dieser Abhängigkeit zu erhalten. 

Sie müssen [die Sprachversion des Compilers konfigurieren](../language-reference/configure-language-version.md) und die Version auswählen, um die neuesten Features in einer Punktversion zu verwenden.

* [C# 7.3](csharp-7-3.md):
  - Auf dieser Seite werden die neuesten Funktionen der Programmiersprache C# vorgestellt. C# 7.3 steht aktuell in [Visual Studio 2017 Version 15.7](https://visualstudio.microsoft.com/vs/whatsnew/) und im [.NET Core 2.1 SDK 2.1.300 RC1](../../core/whats-new/index.md) zur Verfügung.
* [C# 7.2](csharp-7-2.md):
  - Auf dieser Seite werden die Features vorgestellt, die in C# hinzugefügt wurden. C# 7.2 steht aktuell in [Visual Studio 2017 Version 15.5](https://visualstudio.microsoft.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) zur Verfügung.
* [C# 7.1](csharp-7-1.md):
  - Auf dieser Seite werden die Features vorgestellt, die in C# 7.1 hinzugefügt wurden. Diese Features wurden in [Visual Studio 2017 version 15.3](https://visualstudio.microsoft.com/vs/whatsnew/) und im [.NET Core 2.0 SDK](../../core/whats-new/index.md) hinzugefügt.
* [C# 7.0](csharp-7.md):
  - Auf dieser Seite werden die Features vorgestellt, die in C# 7.0 hinzugefügt wurden. Diese Features wurden in [Visual Studio 2017](https://visualstudio.microsoft.com/vs/whatsnew/) und in [.NET Core 1.0](../../core/whats-new/index.md) und höher hinzugefügt.
* [C# 6](csharp-6.md):
  - Auf dieser Seite werden die Funktionen vorgestellt, die in C# 6 eingefügt wurden. Diese Funktionen stehen für Windows-Entwickler in Visual Studio 2015 zur Verfügung; Entwickler, die C# unter macOS und Linux verwenden, können dazu .NET Core 1.0 nutzen.
* [Plattformübergreifender Support](../../core/index.md):
  - C# kann aufgrund des .NET Core Supports auf mehreren Plattformen ausgeführt werden. Wenn Sie C# unter macOS oder unter einer der vielen unterstützten Linux-Distributionen ausprobieren möchten, informieren Sie sich über .NET Core.
* [.NET Compiler Platform SDK](../roslyn-sdk/index.md):
  - Mit dem .NET Compiler Platform SDK können Sie Code zur statischen Analyse von C#-Code schreiben. Sie können diese APIs verwenden, um potenzielle Fehler oder schlechte Methoden zu erkennen, Fehlerkorrekturen vorzuschlagen und diese sogar zu implementieren.

## <a name="previous-versions"></a>Frühere Versionen

Im Folgenden sind die Hauptfunktionen aufgelistet, die mit vorherigen Versionen von C# und Visual Studio .NET eingeführt wurden.

* Visual Studio .NET 2013:
  - Diese Version von Visual Studio enthält Fehlerkorrekturen, Leistungsoptimierungen und eine Technologievorschau der .NET Compiler Platform („Roslyn“), die zum [.NET Compiler Platform SDK](../roslyn-sdk/index.md) wurde.
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
