---
title: Was ist verwalteter Code?
description: Bei verwaltetem Code handelt es sich um Code, dessen Ausführung von einer Runtime verwaltet wird, der Common Language Runtime (CLR).
ms.date: 06/20/2016
ms.assetid: 20bb7ea8-192e-4a96-8ef3-e10e1950fd3d
ms.openlocfilehash: 3e2a6576f84890afd35d74b2f0f5fb352a90236a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825896"
---
# <a name="what-is-managed-code"></a>Was ist „verwalteter Code“?

Bei der Arbeit mit .NET begegnen Sie häufig dem Begriff „verwalteter Code“. In diesem Dokument wird erläutert, was dieser Begriff bedeutet, und es werden zusätzliche Informationen dazu bereitgestellt.

Sehr einfach ausgedrückt, ist verwalteter Code genau das, was der Name besagt: Code, dessen Ausführung von einer Runtime verwaltet wird. In diesem Fall wird die betreffende Runtime als **Common Language Runtime** oder CLR bezeichnet, unabhängig von der Implementierung (z. B. [Mono](https://www.mono-project.com/), .NET Framework oder .NET Core/.NET 5 und höher). Die CLR übernimmt die Aufgabe, den verwalteten Code in Computercode zu kompilieren und dann auszuführen. Darüber hinaus bietet die Common Language Runtime mehrere wichtige Dienste wie die automatische Arbeitsspeicherverwaltung, Sicherheitsgrenzen, Typsicherheit usw.

Vergleichen Sie dies mit der Art und Weise, auf die Sie ein C-/C++-Programm ausführen, dem sogenannten „nicht verwalteten Code“. Im nicht verwalteten Bereich ist der Programmierer für nahezu alles zuständig. Das tatsächliche Programm ist im Wesentlichen eine Binärdatei, die vom Betriebssystem in den Arbeitsspeicher geladen und gestartet wird. Alles Übrige, von der Arbeitsspeicherverwaltung bis hin zu den Sicherheitsaspekten, liegt in der Verantwortung des Programmierers.

Verwalteter Code wird in einer der allgemeinen Sprachen geschrieben, die auf .NET ausgeführt werden können, z.B. C#, Visual Basic, F# und andere. Wenn Sie in diesen Sprachen geschriebenen Code mit ihrem jeweiligen Compiler kompilieren, erhalten Sie keinen Computercode. Sie erhalten Code in einer Zwischensprache, **Intermediate Language**, der von der Runtime kompiliert und ausgeführt wird. C++ ist die einzige Ausnahme von dieser Regel, da diese Sprache auch native, nicht verwaltete Binärdateien erstellen kann, die unter Windows ausgeführt werden.

## <a name="intermediate-language--execution"></a>Zwischensprache (Intermediate Language) und Ausführung

Was ist eine Zwischensprache (Intermediate Language, kurz IL)? Dies ist ein Produkt der Kompilierung von Code, der in allgemeinen .NET-Sprachen geschrieben wurde. Nachdem Sie den Code kompiliert haben, der in einer dieser Sprachen geschrieben wurde, erhalten Sie eine Binärdatei, die aus IL besteht. Beachten Sie unbedingt, dass der IL-Code unabhängig von einer bestimmten Sprache ist, die auf der Runtime ausgeführt wird. Es gibt sogar eine separate Spezifikation dafür, die Sie bei Interesse nachlesen können.

Nachdem Sie IL-Code aus dem allgemeinen Code erstellt haben, möchten Sie diesen höchstwahrscheinlich ausführen. An dieser Stelle übernimmt die CLR und startet den Prozess der **Just-In-Time**-Kompilierung Ihres Codes aus der Zwischensprache in Computercode, der dann auf einer CPU ausgeführt werden kann. Auf diese Weise ist die CLR genau über den Status Ihres Codes informiert und kann ihn effektiv _verwalten_.

Intermediate Language wird auch als Common Intermediate Language (CIL) oder Microsoft Intermediate Language (MSIL) bezeichnet.

## <a name="unmanaged-code-interoperability"></a>Interoperabilität mit nicht verwaltetem Code

Natürlich erlaubt die CLR ein Überschreiten der Grenzen zwischen dem verwaltetem und dem nicht verwaltetem Bereich, und es gibt selbst in den [Basisklassenbibliotheken](framework-libraries.md) eine Menge Code, der diese Möglichkeit nutzt. Dies wird als **Interoperabilität** oder kurz als **Interop** bezeichnet. Durch diese Möglichkeit können Sie beispielsweise eine nicht verwaltete Bibliothek paketieren und aufrufen. Allerdings müssen Sie bei dieser Vorgehensweise beachten, dass die eigentliche Verwaltung der Ausführung wieder beim nicht verwalteten Code liegt, sobald der Code die Grenzen der Runtime überschreitet, und dass die Ausführung daher denselben Einschränkungen unterliegt.

In ähnlicher Weise ist C# eine Sprache, die Ihnen die Verwendung nicht verwalteter Konstrukte, z.B. Zeiger, direkt im Code erlaubt, indem Sie den so genannten **unsicheren Kontext** nutzen. Dieser bezeichnet einen Teil des Codes, dessen Ausführung nicht von der CLR verwaltet wird.

## <a name="more-resources"></a>Weitere Ressourcen

* [Übersicht über .NET Framework](../framework/get-started/overview.md)
* [Unsicherer Code und Zeiger](../csharp/programming-guide/unsafe-code-pointers/index.md)
* [Native Interoperabilität](./native-interop/index.md)
