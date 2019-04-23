---
ms.openlocfilehash: 6ed7438a7f6e7710fcce03c8260a1360143f8d93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235493"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>Hashtable und ähnlich sortierte Auflistungsobjekte können von SoapFormatter nicht deserialisiert werden

|   |   |
|---|---|
|Details|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> garantiert nicht dafür, dass unter einer .NET Framework-Version serialisierte Objekte erfolgreich unter einer anderen Version deserialisiert werden können. Insbesondere einige sortierte Auflistungen (z.B. <xref:System.Collections.Hashtable?displayProperty=name>) haben Member zwischen 4.0 und 4.5 hinzugefügt, sodass Objekte dieser Typen nicht mit .NET Framework 4.0 deserialisiert werden können, wenn sie mit .NET Framework 4.5 serialisiert wurden. Beachten Sie, dass kein Problem auftritt, wenn die serialisierten Daten mit derselben Version von .NET Framework sowohl serialisiert als auch deserialisiert werden.|
|Vorschlag|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> -Serialisierung sollte durch die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name>-Serialisierung oder durch <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> ersetzt werden, um .NET Framework-Änderungen verarbeiten zu können.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
