---
title: Serialisierung in .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 13ba804e76a64c6a0b32ba5a203258e76c209ff4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644914"
---
# <a name="serialization-in-net"></a>Serialisierung in .NET
Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann. Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert. Zusammen ermöglichen es diese Prozesse, dass Daten einfach gespeichert und übertragen werden.  
  
Zwei Serialisierungstechnologien für .NET-Funktionen:  
  
- Bei der binären Serialisierung wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern. So können Sie z.&amp;#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren. Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren. Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.  
  
- Bei der XML-Serialisierung werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten. Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken. Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar. Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
[Vorgehensweise-Themen zur Serialisierung](../../../docs/standard/serialization/serialization-how-to-topics.md)  
Enthält Links zu Gewusst-wie-Themen in diesem Abschnitt.
  
[Binäre Serialisierung](../../../docs/standard/serialization/binary-serialization.md)  
Beschreibt den binären Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.

[XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
Beschreibt den XML- und SOAP-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.

[Serialisierungstools](../../../docs/standard/serialization/serialization-tools.md)  
Diese Tools sind hilfreich bei der Entwicklung von Serialisierungscode.

[Serialisierungsbeispiele](../../../docs/standard/serialization/serialization-samples.md)  
In den Beispielen wird veranschaulicht, wie die Serialisierung stattfindet.

## <a name="reference"></a>Referenz
<xref:System.Runtime.Serialization> Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.
  
<xref:System.Xml.Serialization>  
Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.