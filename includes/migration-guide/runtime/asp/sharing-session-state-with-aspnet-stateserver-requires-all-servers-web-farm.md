---
ms.openlocfilehash: 0fe07ac21effacffc56d37ccb46a121f443acd20
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620177"
---
### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>Für das Freigeben des Sitzungszustands mit Asp.Net StateServer müssen alle Server in der Webfarm dieselbe .NET Framework-Version verwenden

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

-<xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|
