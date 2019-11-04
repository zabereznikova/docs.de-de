---
ms.openlocfilehash: e9278320ee3fdf9e6b89698d187f047c309ea791
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198444"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt.

Das Feld [HandshakeProtocol.SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) wurde entfernt und durch eine Hilfsmethode ersetzt, die eine erfolgreiche Handshakeantwort für ein bestimmtes `IHubProtocol` generiert.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`HandshakeProtocol.SuccessHandshakeData` war ein `public static ReadOnlyMemory<byte>`-Feld.

#### <a name="new-behavior"></a>Neues Verhalten

`HandshakeProtocol.SuccessHandshakeData` wurde durch eine `static` `GetSuccessfulHandshake(IHubProtocol protocol)`-Methode ersetzt, die basierend auf dem angegebenen Protokoll ein `ReadOnlyMemory<byte>` zurückgibt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der _Handshakeantwort_ wurden zusätzliche Felder hinzugefügt, die nicht konstant sind und je nach ausgewähltem Protokoll abweichen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Keine Dieser Typ ist nicht für die Verwendung in Benutzercode vorgesehen. Er ist `public`, damit er von SignalR-Server und -Client gemeinsam verwendet werden kann. Er kann auch von SignalR-Kundenclients verwendet werden, die in .NET geschrieben wurden. **Benutzer** von SignalR sollten von dieser Änderung nicht betroffen sein.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
