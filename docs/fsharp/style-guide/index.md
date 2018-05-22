---
title: Stilvorgaben [F#]
description: Erfahren Sie, die fünf Prinzipien von gute f#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: 6d8c1336ca991040a8f6e13290d209cb3b70054d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="f-style-guide"></a>Stilvorgaben [F#]

In den folgenden Artikeln wird beschrieben, Richtlinien für die Formatierung f#-Code und befassen Leitfaden für die Funktionen der Sprache und wie sie verwendet werden soll.

Dieser Leitfaden wurde basierend auf formuliert wurde die Verwendung von f# in großen Codebasen, mit einer unterschiedlichen Gruppe Programmierer mit sich bringen. In dieser Anleitung wird im Allgemeinen führt zu einer erfolgreichen Verwendung von f# und Frustrations minimiert, wenn Anforderungen für Programme mit der Zeit ändern.

## <a name="five-principles-of-good-f-code"></a>Fünf Prinzipien von gutem Code [F#]

Sie sollten die folgenden Prinzipien jederzeit bedenken, die Sie Schreiben von f#-Code, vor allem bei Systemen, die im Laufe der Zeit ändern. Jedes Datenelement in weiteren Artikeln Anleitung ist, diese fünf Punkte.

1. **Gute f#-Code ist kompakt und aussagekräftig**

    F# bietet viele Features, mit denen Sie Aktionen in weniger Zeilen des Codes und Wiederverwenden von generische Funktionen. Die f#-Kernbibliothek enthält außerdem viele nützliche Typen und Funktionen zum Arbeiten mit gemeinsamen Auflistungen von Daten. Als allgemeine Regel Wenn Sie eine Lösung eines Problems weniger Codezeilen express können werden andere Entwickler (oder die zukünftige Self) wertschätzenden. Es wird auch empfohlen, dass die Verwendung einer Bibliothek, z. B. FSharp.Core verwenden und die [vast .NET Bibliotheken](https://docs.microsoft.com/dotnet/api/) , die F#-ausgeführt wird, oder ein Drittanbieter-Paket auf [NuGet](https://www.nuget.org/) müssen Sie eine nicht triviale Aufgabe auszuführen.

2. **Gute f#-Code ist interoperabel**

    Interoperation kann mehrere Formen annehmen, einschließlich Code in verschiedenen Sprachen nutzen. Die Grenzen des Codes, die andere Aufrufer mit Zusammenwirken sind wichtige Teile, richtig machen. Wenn Sie f# schreiben, sollte immer Denken Sie über wie in anderen Code in den Code aufruft, die Sie z. B., wenn sie dies in einer anderen Sprache wie c# schreiben. Die [f# Komponente Entwurfsrichtlinien](component-design-guidelines.md) Interoperabilität im Detail beschreiben.

3. **Gute f#-Code wird der Objekt-Programmierung verwenden, die nicht Objekten Ausrichtung**

    F# bietet die vollständige Unterstützung für die Programmierung mit Objekten in .NET einschließlich [Klassen](../language-reference/classes.md), [Schnittstellen](../language-reference/interfaces.md), [Zugriffsmodifizierer](../language-reference/access-control.md), [abstrakte Klassen](../language-reference/abstract-classes.md)und so weiter. Für komplexere Funktionscode, z. B. Funktionen, die Kontext-fähig sein muss können Objekte leicht kontextbezogenen Informationen in einer Weise kapseln, die Funktionen nicht. Funktionen, wie [optionale Parameter](../language-reference/members/methods.md#optional-arguments) und [überladen](../language-reference/members/methods.md#overloaded-methods) Verbrauch dieser Funktionalität für Aufrufer auch zu unterstützen.

4. **Gute f#-Code ausführt, auch ohne das Verfügbarmachen von mutation**

    Es ist bekannt, dass zum Schreiben von Code für hohe Leistung Sie Mutation verwenden müssen. Es ist, wie Computer, nachdem alle funktionieren. Solcher Code ist häufig fehleranfällig und schwierig zu richtig machen. Vermeiden Sie Verfügbarmachen von Mutation Aufrufern. Suchen Sie eine funktionsfähige-Schnittstelle, über eine Mutation-basierte Implementierung.

5. **Gute f#-Code ist toolfähig**

    Tools für die Arbeit in großen Codebasen unschätzbarem Wert sind, können Sie f#-Code schreiben, sodass sie effektiver mit F#-Sprache Tools verwendet werden kann. Ein Beispiel wird sichergestellt, dass Sie mit dem Punkt freien Format Programmierung, übertreiben nicht so, dass die Zwischenwerte mit einem Debugger überprüft werden können. Ein weiteres Beispiel verwendeten [XML-Dokumentationskommentare](../language-reference/xml-documentation.md) Konstrukte beschreiben, sodass diese Kommentare in QuickInfos im Editor an der Aufrufsite angezeigt werden können. Stets Bedenken Sie, wie Code lesen, navigiert, debuggt, und von anderen Programmierer mit den Tools bearbeitet.

## <a name="next-steps"></a>Nächste Schritte

Die [f#-Code, die Formatierung von Richtlinien](formatting.md) bieten eine Anleitung zum Code formatieren, sodass sie leicht zu lesen ist.

Die [f# Codekonventionen](conventions.md) bieten eine Anleitung für F#-Programmierung Idiome, das die langfristige Wartung größere f# hilft Codebasen.

Die [f# Komponente Entwurfsrichtlinien](component-design-guidelines.md) bieten eine Anleitung zum Erstellen von F#-Komponenten, z. B. Bibliotheken.
