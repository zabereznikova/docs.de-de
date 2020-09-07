---
ms.openlocfilehash: fccf349517133245ec85ae3c25cedbfb27a7dd8b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497216"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Die Replace-Methode in OData-URLs ist standardmäßig deaktiviert

#### <a name="details"></a>Details

Ab .NET Framework 4.5 ist die Replace-Methode in OData-URLs standardmäßig deaktiviert. Wenn „Replace“ für OData (jetzt standardmäßig) deaktiviert ist, schlagen alle Benutzeranforderungen fehl, einschließlich der Ersetzungsfunktionen (die nicht üblich sind).

#### <a name="suggestion"></a>Vorschlag

Wenn die Replace-Methode erforderlich ist (was nicht üblich ist), kann sie über die Konfigurationseinstellung <xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=fullName> erneut aktiviert werden. Eine aktivierte Replace-Methode kann jedoch Sicherheitslücken öffnen und sollte nur nach sorgfältiger Prüfung verwendet werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Data.Services.DataService%601?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``T:System.Data.Services.DataService`1``

-->
