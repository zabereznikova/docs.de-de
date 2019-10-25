---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394271"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Caching: CompactOnMemoryPressure-Eigenschaft wurde entfernt.

Die [veralteten MemoryCacheOptions-APIs](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) wurden im Release ASP.NET Core 3.0 entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

Diese Änderung resultiert aus [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221). Weitere Informationen finden Sie unter [aspnet/Extensions#1062](https://github.com/aspnet/Extensions/issues/1062).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft war verfügbar.

#### <a name="new-behavior"></a>Neues Verhalten

Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft wurde entfernt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die automatische Komprimierung des Caches hat Probleme verursacht. Um unerwartetes Verhalten zu vermeiden, sollte der Cache nur bei Bedarf komprimiert werden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Um den Cache zu komprimieren, führen Sie eine Umwandlung in `MemoryCache` durch und rufen bei Bedarf `Compact` auf.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
