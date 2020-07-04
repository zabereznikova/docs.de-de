---
title: 'Serialisierung: .NET'
description: Dieser Artikel enthält Informationen zu .NET-Serialisierungstechnologien, einschließlich binärer Serialisierung, XML- und SOAP-Serialisierung und JSON-Serialisierung.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840303"
---
# <a name="serialization-in-net"></a>Serialisierung in .NET

Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann. Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert. Zusammen ermöglichen es diese Prozesse, dass Daten gespeichert und übertragen werden können.  
  
.NET verwendet die folgenden Serialisierungstechnologien:  
  
- Bei der [binären Serialisierung](binary-serialization.md) wird die Typtreue beibehalten. Dies ist nützlich, um den Zustand eines Objekts zwischen verschiedenen Aufrufen einer Anwendung zu speichern. So können Sie z.&#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren. Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren. Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.  
  
- Bei der [XML- und SOAP-Serialisierung](xml-and-soap-serialization.md) werden nur öffentliche Eigenschaften und Felder serialisiert, und die Typtreue wird nicht beibehalten. Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken. Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar. Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.  
  
- Bei der [JSON-Serialisierung](system-text-json-overview.md) werden nur öffentliche Eigenschaften serialisiert, und die Typtreue wird nicht beibehalten. JSON ist ein offener Standard und stellt eine attraktive Möglichkeit für den Datenaustausch im Internet dar.

## <a name="reference"></a>Referenz

<xref:System.Runtime.Serialization>  
Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.
  
<xref:System.Xml.Serialization>  
Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.

<xref:System.Text.Json>  
Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im JSON-Format verwendet werden können.
