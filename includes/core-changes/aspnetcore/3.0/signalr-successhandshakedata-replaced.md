---
ms.openlocfilehash: 05aec429e28ef74515ef6988d5b064e6d16b7c1b
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90680025"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a>SignalR: HandshakeProtocol.SuccessHandshakeData wurde ersetzt.

Das Feld [HandshakeProtocol.SuccessHandshakeData](https://github.com/dotnet/aspnetcore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) wurde entfernt und durch eine Hilfsmethode ersetzt, die eine erfolgreiche Handshakeantwort für ein bestimmtes `IHubProtocol` generiert.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

`HandshakeProtocol.SuccessHandshakeData` war ein `public static ReadOnlyMemory<byte>`-Feld.

#### <a name="new-behavior"></a>Neues Verhalten

`HandshakeProtocol.SuccessHandshakeData` wurde durch eine `static` `GetSuccessfulHandshake(IHubProtocol protocol)`-Methode ersetzt, die basierend auf dem angegebenen Protokoll ein `ReadOnlyMemory<byte>`-Element zurückgibt.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der _Handshakeantwort_ wurden zusätzliche Felder hinzugefügt, die nicht konstant sind und je nach ausgewähltem Protokoll abweichen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Keine Dieser Typ ist nicht für die Verwendung in Benutzercode vorgesehen. Er ist `public`, damit er von SignalR-Server und -Client gemeinsam verwendet werden kann. Er kann auch von SignalR-Kundenclients verwendet werden, die in .NET geschrieben wurden. **Benutzer** von SignalR sollten von dieser Änderung nicht betroffen sein.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=nameWithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
