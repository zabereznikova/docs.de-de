---
title: 'Breaking Change: MulticastOption.Group akzeptiert keine null-Werte'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, wegen dem MulticastOption.Group keinen NULL-Wert mehr akzeptiert.
ms.date: 08/18/2020
ms.openlocfilehash: 164ac8c2c8dd14f9e0758017e54eeb377f88a7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759386"
---
# <a name="multicastoptiongroup-doesnt-accept-a-null-value"></a>MulticastOption.Group akzeptiert keine null-Werte

<xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType> akzeptiert keine `null`-Werte mehr. Wenn Sie die Eigenschaft auf `null` festlegen, wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET können Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft auf `null` festlegen. Wenn die <xref:System.Net.Sockets.MulticastOption>-Klasse später an die <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>-Methode weitergegeben wird, löst die Runtime eine <xref:System.NullReferenceException>-Klasse aus.

In .NET 5.0 und höher wird eine <xref:System.ArgumentNullException>-Klasse ausgelöst, wenn Sie die Eigenschaft auf `null` festlegen.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Eigenschaft wurde so aktualisiert, dass sie eine <xref:System.ArgumentNullException>-Klasse ausgibt, wenn der Wert `null` ist, um den Frameworkentwurfsrichtlinien zu entsprechen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Stellen Sie sicher, dass Sie die <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=nameWithType>-Eigenschaft nicht auf `null` festlegen.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Sockets.MulticastOption.Group?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Net.Sockets.MulticastOption.Group`

### Category

Networking

-->
