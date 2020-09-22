---
title: XML- und SOAP-Serialisierung
description: In dieser Übersicht wird die XML-Serialisierung erläutert, mit der Objekte in XML-Streams serialisiert werden können, die der SOAP-Spezifikation entsprechen.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: f7ad7732f929ac3599942c5440b173ea226cca87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544985"
---
# <a name="xml-and-soap-serialization"></a>XML- und SOAP-Serialisierung

Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream konvertiert (serialisiert), der einem bestimmtem XSD (XML Schema Definition)-Dokument entspricht. Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in ein serielles Format (hier XML) konvertiert werden.

Weil XML ein offener Standard ist, kann der XML-Stream plattformunabhängig bei Bedarf von jeder Anwendung verarbeitet werden. Beispielsweise verwenden mit ASP.NET erstellte Webdienste die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Erstellen von XML-Sstreams, die zur Übermittlung von Daten zwischen XML-Webdienstanwendungen über das Internet oder ein Intranet dienen. Umgekehrt wird bei der Deserialisierung das Objekt aus einem XML-Stream rekonstruiert.

Durch die XML-Serialisierung können auch Objekte in XML-Streams serialisiert werden, die der SOAP-Spezifikation entsprechen. SOAP ist ein auf XML basierendes Protokoll, das speziell für die Weitergabe von Prozeduraufrufen unter Verwendung von XML entwickelt wurde.

Sie können mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse Objekte serialisieren und deserialisieren. Verwenden Sie das XML Schema Definition-Tool, um die zu serialisierenden Klassen zu erstellen.

## <a name="see-also"></a>Siehe auch

- [Binäre Serialisierung](binary-serialization.md)
- [Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
