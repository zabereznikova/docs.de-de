---
title: 'Serialisierung: .net'
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053349"
---
# <a name="serialization-in-net"></a>Serialisierung in .NET

Unter Serialisierung wird das Konvertieren des Zustands eines Objekts in eine Form verstanden, die erhalten oder transportiert werden kann. Das Gegenstück zur Serialisierung ist die Deserialisierung, die einen Stream in ein Objekt konvertiert. Diese Prozesse ermöglichen es Ihnen, Daten zu speichern und zu übertragen.  
  
.Net bietet die folgenden Serialisierungstechnologien:  
  
- Die [binäre Serialisierung](binary-serialization.md) behält die Typtreue bei, was für die Beibehaltung des Zustands eines Objekts zwischen verschiedenen Aufrufen einer Anwendung nützlich ist. So können Sie z.&#160;B. ein Objekt für unterschiedliche Anwendungen freigeben, indem Sie es in die Zwischenablage serialisieren. Sie können ein Objekt in einen Stream, einen Datenträger, den Arbeitsspeicher, über das Netzwerk usw. serialisieren. Die Serialisierung wird vom Remotingsystem dazu verwendet, um Objekte "als Wert" von einem Computer bzw. einer Anwendungsdomäne an einen anderen Computer bzw. eine andere Anwendungsdomäne zu übergeben.  
  
- Die [XML-und SOAP-Serialisierung](xml-and-soap-serialization.md) serialisiert nur öffentliche Eigenschaften und Felder und bewahrt die Typtreue nicht. Dies ist hilfreich, wenn Daten bereitgestellt oder benutzt werden sollen, ohne die Anwendung, welche die Daten verwendet, zu beschränken. Da XML ein offener Standard ist, stellt XML eine attraktive Möglichkeit für den Datenaustausch im Internet dar. Ebenso ist SOAP ein offener Standard und damit auch eine attraktive Alternative.  
  
- Bei der [JSON-Serialisierung](system-text-json-overview.md) werden nur öffentliche Eigenschaften serialisiert, und die Typtreue wird nicht beibehalten. JSON ist ein offener Standard, der für die gemeinsame Nutzung von Daten im Internet geeignet ist.

## <a name="reference"></a>Referenz

<xref:System.Runtime.Serialization>  
Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.
  
<xref:System.Xml.Serialization>  
Enthält Klassen, die zur Serialisierung von Objekten in Dokumente oder Streams im XML-Format verwendet werden können.

<xref:System.Text.Json>  
Enthält Klassen, die zum Serialisieren von Objekten in Dokumente oder Streams im JSON-Format verwendet werden können.
