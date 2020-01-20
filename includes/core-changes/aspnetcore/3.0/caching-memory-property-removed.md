---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901986"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Zwischenspeicherung: CompactOnMemoryPressure-Eigenschaft wurde entfernt.

Die [veralteten MemoryCacheOptions-APIs](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18) wurden im Release ASP.NET Core 3.0 entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

Diese Änderung resultiert aus [aspnet/Caching#221](https://github.com/aspnet/Caching/issues/221). Weitere Informationen finden Sie unter [dotnet/extensions#1062](https://github.com/dotnet/extensions/issues/1062).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft war verfügbar.

#### <a name="new-behavior"></a>Neues Verhalten

Die `MemoryCacheOptions.CompactOnMemoryPressure`-Eigenschaft wurde entfernt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die automatische Komprimierung des Caches hat Probleme verursacht. Um unerwartetes Verhalten zu vermeiden, sollte der Cache nur bei Bedarf komprimiert werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Um den Cache zu komprimieren, führen Sie eine Umwandlung in `MemoryCache` durch und rufen bei Bedarf `Compact` auf.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
