---
title: F#-Styleguide
description: Lernen Sie die fünf Prinzipien von gutem F#-Code kennen.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223648"
---
# <a name="f-style-guide"></a>F#-Styleguide

In den folgenden Artikeln werden die Richtlinien für das Formatieren von F#-Code und die aktuellen Empfehlungen für die Funktionen der Sprache und deren Verwendung beschrieben.

Diese Anleitung wurde von einem diversen Team von Programmierern auf Grundlage seiner Arbeit an großen F#-Codebasen formuliert. Die Anleitung führt im Allgemeinen zu einer erfolgreichen Verwendung von F# und einem souveränen Umgang mit sich ändernden Anforderungen an Programme.

## <a name="five-principles-of-good-f-code"></a>Die fünf Prinzipien von gutem F#-Code

Beachten Sie beim Schreiben von F#-Code die folgenden Prinzipien – insbesondere bei Systemen, die sich im Laufe der Zeit ändern. Jede Anleitung in weiteren Artikeln beruht auf diesen fünf Punkten.

1. **Guter F#-Code ist kompakt, aussagekräftig und leicht kombinierbar**

    F# verfügt über viele Funktionen, mit denen Sie Aktionen mit weniger Codezeilen programmieren und generische Funktionen wiederverwenden können. Die F#-Kernbibliothek enthält außerdem viele nützliche Typen und Funktionen für die Arbeit mit allgemeinen Datensammlungen. Die Zusammenstellung Ihrer eigenen Funktionen und der Funktionen in der F#-Kernbibliothek (oder anderen Bibliotheken) ist Teil der routinemäßigen idiomatischen F#-Programmierung. Als allgemeine Regel gilt: Wenn Sie eine Lösung für ein Problem in weniger Codezeilen formulieren können, werden Ihnen andere Entwickler (und Sie selbst zu einem späteren Zeitpunkt) dankbar sein. Außerdem wird dringend empfohlen, dass Sie eine Bibliothek wie FSharp.Core, die [umfangreichen .NET-Bibliotheken](../../../api/index.md) von F# oder ein Drittanbieterpaket auf [NuGet](https://www.nuget.org/) verwenden, wenn Sie eine nicht triviale Aufgabe ausführen müssen.

2. **Guter F#-Code ist interoperabel**

    Interoperabilität hat viele Facetten, z. B. die Verwendung von Code in verschiedenen Sprachen. Die Schnittstellen Ihres Codes, die von externen Aufrufen verwendet werden, müssen unbedingt korrekt sein, auch wenn die Aufrufe ebenfalls in F# erfolgen. Wenn Sie in F# programmieren, sollten Sie sich immer überlegen, wie Ihr Code aus anderem Code aufgerufen wird, auch wenn dazu eine andere Sprache als F# verwendet wird. In den [Entwurfsrichtlinien für eine F#-Komponente](component-design-guidelines.md) wird das Thema Interoperabilität ausführlich behandelt.

3. **Guter F#-Code nutzt Objektprogrammierung, nicht Objektorientierung**

    F# bietet umfassende Unterstützung für die Programmierung mit Objekten in .NET wie [Klassen](../language-reference/classes.md), [Schnittstellen](../language-reference/interfaces.md), [Zugriffsmodifizierer](../language-reference/access-control.md) und [abstrakte Klassen](../language-reference/abstract-classes.md). Für komplizierteren funktionalen Code, z. B. bei Funktionen, die kontextabhängig sein müssen, können Objekte Kontextinformationen problemlos auf eine Weise kapseln, die mit Funktionen nicht möglich ist. Features wie [optionale Parameter](../language-reference/members/methods.md#optional-arguments) und der sorgfältige Einsatz von [Überladungen](../language-reference/members/methods.md#overloaded-methods) können die Nutzung dieser Funktionalität für Aufrufer vereinfachen.

4. **Guter F#-Code erzielt eine gute Leistung, ohne Mutation verfügbar zu machen**

    Es ist kein Geheimnis, dass Sie Mutation verwenden müssen, um hochleistungsfähigen Code zu schreiben. So funktionieren Computer nun einmal. Solcher Code ist oft fehleranfällig und nicht einfach zu schreiben. Vermeiden Sie es, Mutation für Aufrufer verfügbar zu machen. Stattdessen sollten Sie eine [funktionale Schnittstelle erstellen, die eine Mutationsimplementierung verbirgt](conventions.md#performance), wenn es auf die Leistung ankommt.

5. **Guter F# Code ist toolfreundlich**

    Tools sind für die Arbeit an großen Codebasen äußerst nützlich, und Sie können F#-Code so schreiben, dass er effektiver mit Tools für die F#-Sprache verwendet werden kann. Beispielsweise sollten Sie möglichst keinen punktfreien Programmierstil verfolgen, damit Zwischenwerte mit dem Debugger überprüft werden können. Ein weiteres Beispiel ist die Verwendung [XML-Dokumentationskommentaren](../language-reference/xml-documentation.md) zur Beschreibung von Konstrukten, sodass diese Kommentare in Editoren am Aufrufort als QuickInfos angezeigt werden können. Denken Sie immer daran, wie Ihr Code von anderen Programmierern und deren Tools gelesen, durchsucht, debuggt und bearbeitet werden kann.

## <a name="next-steps"></a>Nächste Schritte

Die [Richtlinien für das Formatieren von F#-Code](formatting.md) enthalten Empfehlungen für gut lesbaren Code.

Die [Codekonventionen für F#](conventions.md) enthalten Empfehlungen für F#-Sprachkonstrukte, die eine Wartung größerer F#-Codebasen auf Dauer vereinfachen.

Die [Entwurfsrichtlinien für eine F#-Komponente](component-design-guidelines.md) enthalten Empfehlungen zum Erstellen von F#-Komponenten wie Bibliotheken.
