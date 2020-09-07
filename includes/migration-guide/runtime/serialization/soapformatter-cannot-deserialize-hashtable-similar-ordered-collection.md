---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496746"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>Hashtable und ähnlich sortierte Auflistungsobjekte können von SoapFormatter nicht deserialisiert werden

#### <a name="details"></a>Details

<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> garantiert nicht dafür, dass unter einer .NET Framework-Version serialisierte Objekte erfolgreich unter einer anderen Version deserialisiert werden können. Insbesondere einige sortierte Auflistungen (z.B. <xref:System.Collections.Hashtable?displayProperty=fullName>) haben Member zwischen 4.0 und 4.5 hinzugefügt, sodass Objekte dieser Typen nicht mit .NET Framework 4.0 deserialisiert werden können, wenn sie mit .NET Framework 4.5 serialisiert wurden. Beachten Sie, dass kein Problem auftritt, wenn die serialisierten Daten mit derselben Version von .NET Framework sowohl serialisiert als auch deserialisiert werden.

#### <a name="suggestion"></a>Vorschlag

Die <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName>-Serialisierung sollte durch die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName>-Serialisierung oder durch <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> ersetzt werden, um .NET Framework-Änderungen verarbeiten zu können.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
