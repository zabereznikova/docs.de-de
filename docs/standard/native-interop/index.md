---
title: Native Interoperabilität – .NET
description: Erfahren Sie, wie Sie eine Verknüpfung mit nativen Komponenten in .NET herstellen.
ms.date: 01/18/2019
ms.openlocfilehash: 330466d74cc268214f74c4f575e6a2961f678972
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706334"
---
# <a name="native-interoperability"></a>Native Interoperabilität

Im folgenden Artikel werden mehrere Möglichkeiten zur Umsetzung der nativen Interoperabilität in .NET vorgestellt.

Es gibt einige Gründe für das Aufrufen von nativem Code:

- Betriebssysteme enthalten viele APIs, die in den verwalteten Klassenbibliotheken nicht vorhanden sind. Ein gutes Beispiel hierfür ist der Zugriff auf Verwaltungsfunktionen für Hardware oder das Betriebssystem.
- Die Kommunikation mit anderen Komponenten, die ABIs im C-Stil (native ABIs) enthalten oder erstellen können, z. B. Java-Code, der über [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) oder eine andere verwaltete Sprache verfügbar gemacht wird, die eine native Komponente erstellen kann.
- Unter Windows werden für den Großteil der installierten Software (z. B. die Microsoft Office-Suite) COM-Komponenten registriert, die für die Programme stehen und Entwicklern deren Automatisierung oder Verwendung ermöglichen. Auch hierfür ist native Interoperabilität erforderlich.

Die obige Liste deckt nicht alle möglichen Situationen und Szenarios ab, in denen Entwickler eine Schnittstelle mit nativen Komponenten bevorzugen oder benötigen würden. Die .NET-Klassenbibliothek verwendet zum Beispiel die Unterstützung für native Interoperabilität, um eine große Anzahl ihrer APIs zu implementieren, z.B. die Unterstützung und Bearbeitung der Konsole, Dateisystemzugriff und mehr. Nun wissen Sie jedoch, dass Sie diese Option bei Bedarf verwenden können.

> [!NOTE]
> Die meisten Beispiele in diesem Abschnitt werden für alle drei unterstützten Plattformen für .NET Core (Windows, Linux und macOS) aufgeführt. Bei einigen kurzen und anschaulichen Beispielen wird allerdings nur ein Beispiel gezeigt, das Windows-Dateinamen und -Erweiterungen (d.h. „DLL“ für Bibliotheken) verwendet. Dies wurde nur der Einfachheit halber so gehandhabt und bedeutet nicht, dass diese Funktionen unter Linux oder macOS nicht verfügbar sind.

## <a name="see-also"></a>Siehe auch

- [Plattformaufruf (P/Invoke)](pinvoke.md)
- [Marshalling von Typen](type-marshaling.md)
- [Bewährte Methoden für native Interoperabilität](best-practices.md)
