---
ms.openlocfilehash: 80d4bbbfe52ab9685d7ca54f21b80d4b1773da22
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859619"
---
### <a name="webclientcancelasync-doesnt-always-cancel-immediately"></a>WebClient.CancelAsync wird nicht immer sofort abgebrochen

Ab .NET Core 2.0 wird die Anforderung beim Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> nicht sofort abgebrochen, wenn die Antwort mit dem Abrufen begonnen hat.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor wurde durch Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> die Anforderung sofort abgebrochen. Ab .NET Core 2.0 wird die Anforderung beim Aufrufen von <xref:System.Net.WebClient.CancelAsync?displayProperty=nameWithType> nur dann sofort abgebrochen, wenn die Antwort mit dem Abrufen noch nicht begonnen hat. Wenn die Antwort mit dem Abrufen begonnen hat, wird die Anforderung erst abgebrochen, nachdem eine vollständige Antwort gelesen wurde.

Diese Änderung wurde implementiert, weil die <xref:System.Net.WebClient>-API zugunsten von <xref:System.Net.Http.HttpClient> eingestellt wurde.

#### <a name="version-introduced"></a>Eingeführt in Version

2.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie die <xref:System.Net.Http.HttpClient?displayProperty=fullName>-Klasse anstelle von <xref:System.Net.WebClient?displayProperty=fullName>, die veraltet ist.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.WebClient.CancelAsync?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Net.WebClient.CancelAsync`

-->
