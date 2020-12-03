---
title: 'Breaking Change: Entfernung von WinHttpHandler aus der .NET-Runtime'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den WinHttpHandler aus der .NET-Runtime entfernt wurde.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759382"
---
# <a name="winhttphandler-removed-from-net-runtime"></a>Entfernung von WinHttpHandler aus der .NET-Runtime

Die `WinHttpHandler`-Klasse wurde aus der Assembly *System.Net.Http.dll* entfernt. Sie ist jetzt nur als [OOB-NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) (Out-of-Band) verfügbar.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen ist die <xref:System.Net.Http.WinHttpHandler>-Klasse als Teil der .NET-Kernbibliotheken verfügbar. Ab .NET 5.0 ist die <xref:System.Net.Http.WinHttpHandler>-Klasse nur als separat installiertes [NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) verfügbar.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Installieren Sie das [NuGet-Paket „System.Net.Http.WinHttpHandler“](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/). Wenn Sie keine WinHTTP-spezifischen Features benötigen, können Sie stattdessen <xref:System.Net.Http.SocketsHttpHandler> verwenden.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
