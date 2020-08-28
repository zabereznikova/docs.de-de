---
ms.openlocfilehash: 88a0b7e04c7015ca3fa5abd8a6897dafcbe41c49
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557963"
---
### <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group akzeptiert keine null-Werte

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> akzeptiert keine `null`-Werte mehr. Wenn Sie die Eigenschaft auf `null` festlegen, wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET können Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft auf `null` festlegen. Wenn die <xref:System.Net.Sockets.MulticastOption>-Klasse später an die <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>-Methode weitergegeben wird, löst die Runtime eine <xref:System.NullReferenceException>-Klasse aus.

In .NET 5.0 und höher wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst, wenn Sie die Eigenschaft auf `null` festlegen.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Eigenschaft wurde so aktualisiert, dass sie eine <xref:System.ArgumentNullException>-Klasse ausgibt, wenn der Wert `null` ist, um den Frameworkentwurfsrichtlinien zu entsprechen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Stellen Sie sicher, dass Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft nicht auf `null` festlegen.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

-->
