---
title: F#-Styleguide
description: Lernen Sie die fünf Prinzipien des guten F-Codes.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401112"
---
# <a name="f-style-guide"></a>F#-Styleguide

In den folgenden Artikeln werden die Richtlinien für die Formatierung von F-Code und die aktuellen Anleitungen für Features der Sprache und deren Verwendung beschrieben.

Diese Anleitung wurde auf der Grundlage der Verwendung von F- in großen Codebasen mit einer vielzahln Programmierern formuliert. Diese Anleitung führt in der Regel zu einer erfolgreichen Verwendung von F- und Frustrationen, wenn sich die Anforderungen an Programme im Laufe der Zeit ändern.

## <a name="five-principles-of-good-f-code"></a>Fünf Prinzipien des guten F-Codes

Beachten Sie die folgenden Grundsätze bei jedem Schreiben von F-Code, insbesondere in Systemen, die sich im Laufe der Zeit ändern. Aus diesen fünf Punkten ergibt sich jede Anleitung in weiteren Artikeln.

1. **Guter F-Code ist prägnant, ausdrucksstark und komponierbar**

    Es gibt viele Funktionen, mit denen Sie Aktionen in weniger Codezeilen ausdrücken und generische Funktionen wiederverwenden können. Die Kernbibliothek von F- enthält auch viele nützliche Typen und Funktionen für die Arbeit mit allgemeinen Datensammlungen. Die Komposition Ihrer eigenen Funktionen und der Funktionen in der Kernbibliothek (oder anderen Bibliotheken) ist Teil der routinemäßigen idiomamatischen F-Programmierung. Wenn Sie in der Regel eine Lösung für ein Problem in weniger Codezeilen ausdrücken können, werden andere Entwickler (oder Ihr zukünftiges Selbst) dankbar sein. Es wird auch dringend empfohlen, eine Bibliothek wie FSharp.Core, die [umfangreichen .NET-Bibliotheken,](../../../api/index.md) auf denen F- ausgeführt wird, oder ein Drittanbieterpaket auf [NuGet](https://www.nuget.org/) zu verwenden, wenn Sie eine nicht triviale Aufgabe ausführen müssen.

2. **Guter F-Code ist interoperabel**

    Die Zusammenarbeit kann mehrere Formen annehmen, einschließlich des Verwendens von Code in verschiedenen Sprachen. Die Grenzen des Codes, mit denen andere Anrufer zusammenarbeiten, sind wichtige Teile, um richtig zu werden, auch wenn sich die Aufrufer ebenfalls in F' befinden. Wenn Sie F- schreiben, sollten Sie immer darüber nachdenken, wie anderer Code in den Code aufrufen wird, den Sie schreiben, auch wenn er dies aus einer anderen Sprache wie C. tut. In den [Richtlinien für den Komponentenentwurf](component-design-guidelines.md) wird die Interoperabilität ausführlich beschrieben.

3. **Guter F-Code verwendet Objektprogrammierung, nicht Objektausrichtung**

    Die Programmierung mit Objekten in .NET, einschließlich [Klassen,](../language-reference/classes.md) [Schnittstellen,](../language-reference/interfaces.md) [Zugriffsmodifizierern,](../language-reference/access-control.md) [abstrakten Klassen](../language-reference/abstract-classes.md)usw., wird von F- unterstützt. Bei komplizierterem Funktionscode, z. B. Funktionen, die kontextbewusst sein müssen, können Objekte kontextbezogene Informationen problemlos auf eine Weise kapseln, die Funktionen nicht können. Funktionen wie [optionale Parameter](../language-reference/members/methods.md#optional-arguments) und die sorgfältige Verwendung von [Überlastung](../language-reference/members/methods.md#overloaded-methods) können den Verbrauch dieser Funktionalität für Aufrufer erleichtern.

4. **Guter F-Code funktioniert gut, ohne Mutation freizulegen**

    Es ist kein Geheimnis, dass Sie Mutation verwenden müssen, um Hochleistungscode zu schreiben. Es ist, wie Computer funktionieren, schließlich. Ein solcher Code ist oft fehleranfällig und schwierig, richtig zu werden. Vermeiden Sie es, Callern Mutationen auszusetzen. Erstellen Sie stattdessen [eine funktionale Schnittstelle, die eine mutationsbasierte Implementierung ausblendet,](conventions.md#performance) wenn die Leistung entscheidend ist.

5. **Guter F-Code ist werkzeugbar**

    Tools sind für die Arbeit in großen Codebasen von unschätzbarem Wert, und Sie können F-Code so schreiben, dass er effektiver mit den Tools für die Sprache von F verwendet werden kann. Ein Beispiel ist, sicherzustellen, dass Sie es nicht mit einem punktfreien Programmierstil überarbeiten, sodass Zwischenwerte mit einem Debugger überprüft werden können. Ein weiteres Beispiel ist die Verwendung von [XML-Dokumentationskommentaren,](../language-reference/xml-documentation.md) die Konstrukte beschreiben, sodass QuickInfos in Editoren diese Kommentare auf der Aufrufsite anzeigen können. Denken Sie immer darüber nach, wie Ihr Code von anderen Programmierern mit ihren Tools gelesen, navigiert, gedebugcht und bearbeitet wird.

## <a name="next-steps"></a>Nächste Schritte

Die Richtlinien für die [Codeformatierung von F-Code](formatting.md) bieten Anleitungen zum Formatieren von Code, damit er leicht lesbar ist.

Die [F-Codierungskonventionen](conventions.md) bieten Anleitungen für Programmieridiome von F-Programmen, die bei der langfristigen Wartung größerer F-Codebasen helfen.

Die Richtlinien für den Entwurf von Komponenten bieten Anleitungen zum Erstellen von F-Komponenten, z. [B.](component-design-guidelines.md) Bibliotheken.
