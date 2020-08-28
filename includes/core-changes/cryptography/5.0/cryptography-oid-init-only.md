---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558002"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft

Die <xref:System.Security.Cryptography.Oid?displayProperty=fullName>-Klasse, die zum Darstellen von ASN.1-Objektbezeichnerwerten und deren „Anzeigenamen“ verwendet wird, war zuvor vollständig änderbar. Diese Veränderlichkeit wurde oft übersehen oder überraschte Benutzer. Die Eigenschaftensetter lösen jetzt eine <xref:System.PlatformNotSupportedException>-Klasse aus, wenn Sie versuchen, den Wert zu ändern, nachdem dieser bereits zugewiesen wurde.

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen können die Eigenschaftensetter für die <xref:System.Security.Cryptography.Oid>-Klasse verwendet werden, um den Wert der Eigenschaften <xref:System.Security.Cryptography.Oid.FriendlyName> und <xref:System.Security.Cryptography.Oid.Value> zu ändern.

In .NET 5.0 und höheren Versionen können die Eigenschaftensetter nur zum Initialisieren eines Werts verwendet werden. Wenn die Eigenschaft entweder durch einen Konstruktor oder einen vorherigen Aufruf des Eigenschaftensetters über einen Wert verfügt, löst der Eigenschaftensetter immer eine <xref:System.PlatformNotSupportedException>-Klasse aus.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht die Wiederverwendung von <xref:System.Security.Cryptography.Oid>-Objekten als Teil der Rückgabewerte in öffentlichen APIs, um Objektzuordnungsprofile zu reduzieren. Wenn <xref:System.Security.Cryptography.Oid>-Werte als Eingaben verwendet werden, müssen keine temporären „defensiven“ Kopien erstellt werden.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Aktion

Vermeiden Sie die Verwendung der <xref:System.Security.Cryptography.Oid>-Eigenschaftensetter (außer bei der Objektinitialisierung). Verwenden Sie eine neue Instanz, anstatt den Wert für ein vorhandenes Objekt zu ändern, wenn Sie einen neuen Wert darstellen möchten.

#### <a name="category"></a>Kategorie

Kryptografie

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
