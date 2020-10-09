---
ms.openlocfilehash: e450c53008e7562e37518fdfd6872ff9b63b6ac3
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609132"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Für das Freigeben des Sitzungszustands mit ASP.NET StateServer müssen alle Server in der Webfarm dieselbe .NET Framework-Version verwenden

#### <a name="details"></a>Details

Wenn ein <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=fullName>-Sitzungszustand aktiviert wird, müssen alle Server in der jeweiligen Webfarm dieselbe Version von .NET Framework verwenden, damit der Zustand ohne Probleme freigegeben werden kann.

#### <a name="suggestion"></a>Vorschlag

Führen Sie für alle .NET Framework-Versionen auf Webservern, für die ein Zustand freigegeben wird, gleichzeitig ein Upgrade aus.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType>

<!--

#### Affected APIs

- `F:System.Web.SessionState.SessionStateMode.StateServer`

-->
