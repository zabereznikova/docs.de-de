---
title: 'Breaking Change: Cryptography.OID ist funktional ein Nur-init-Setter'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Eigenschaftensetter in der Klasse „Cryptography.Oid“ nun eine Ausnahme auslösen, wenn Sie versuchen, einen Wert zu ändern.
ms.date: 08/16/2020
ms.openlocfilehash: a3b5a393e2a84f7c9a60c2a821ecfda9c6acd2e3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759226"
---
# <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a>Funktionalität von System.Security.Cryptography.Oid mit init-only-Eigenschaft

Die <xref:System.Security.Cryptography.Oid?displayProperty=fullName>-Klasse, die zum Darstellen von ASN.1-Objektbezeichnerwerten und deren „Anzeigenamen“ verwendet wird, war zuvor vollständig änderbar. Diese Veränderlichkeit wurde oft übersehen oder überraschte Benutzer. Die Eigenschaftensetter lösen jetzt eine <xref:System.PlatformNotSupportedException>-Klasse aus, wenn Sie versuchen, den Wert zu ändern, nachdem dieser bereits zugewiesen wurde.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen können die Eigenschaftensetter für die <xref:System.Security.Cryptography.Oid>-Klasse verwendet werden, um den Wert der Eigenschaften <xref:System.Security.Cryptography.Oid.FriendlyName> und <xref:System.Security.Cryptography.Oid.Value> zu ändern.

In .NET 5.0 und höheren Versionen können die Eigenschaftensetter nur zum Initialisieren eines Werts verwendet werden. Wenn die Eigenschaft entweder durch einen Konstruktor oder einen vorherigen Aufruf des Eigenschaftensetters über einen Wert verfügt, löst der Eigenschaftensetter immer eine <xref:System.PlatformNotSupportedException>-Klasse aus.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung ermöglicht die Wiederverwendung von <xref:System.Security.Cryptography.Oid>-Objekten als Teil der Rückgabewerte in öffentlichen APIs, um Objektzuordnungsprofile zu reduzieren. Wenn <xref:System.Security.Cryptography.Oid>-Werte als Eingaben verwendet werden, müssen keine temporären „defensiven“ Kopien erstellt werden.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Vermeiden Sie die Verwendung der <xref:System.Security.Cryptography.Oid>-Eigenschaftensetter (außer bei der Objektinitialisierung). Verwenden Sie eine neue Instanz, anstatt den Wert für ein vorhandenes Objekt zu ändern, wenn Sie einen neuen Wert darstellen möchten.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

### Category

Cryptography

-->
