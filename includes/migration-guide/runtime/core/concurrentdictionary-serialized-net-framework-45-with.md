---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497643"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Ein in .NET Framework 4.5 mit NetDataContractSerializer serialisiertes ConcurrentDictionary-Element kann nicht von .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden

#### <a name="details"></a>Details

Aufgrund von Typänderungen können <xref:System.Collections.Concurrent.ConcurrentDictionary%602>-Objekte, die unter Verwendung von <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> mit .NET Framework 4.5 serialisiert werden, nicht in .NET Framework 4.5.1 oder 4.5.2 deserialisiert werden. Beachten Sie jedoch, dass die Serialisierung mit .NET Framework 4.5.x und die Deserialisierung mit .NET Framework 4.5 funktionieren. Genauso funktioniert die versionsübergreifende Serialisierung in .NET Framework 4.x mit .NET Framework 4.6. Dies hat keine Auswirkungen auf die (De-)Serialisierung einer einzelnen Version von .NET Framework.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie ein <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>-Element zwischen .NET Framework 4.5 und .NET Framework 4.5.1/4.5.2 (de-)serialisieren müssen, sollten Sie statt <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> ein Serialisierungsmodul wie <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> oder <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> verwenden. Das Problem könnte möglicherweise aber auch durch ein Upgrade auf .NET Framework 4.6 gelöst werden, da es in dieser Version behoben wird.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
