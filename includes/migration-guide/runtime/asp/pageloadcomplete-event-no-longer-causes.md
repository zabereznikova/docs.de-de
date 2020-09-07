---
ms.openlocfilehash: a84d72813a46d6bb39f4710b35d2c9dc859e30ef
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496533"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Das Page.LoadComplete-Ereignis führt nicht mehr dazu, dass das System.Web.UI.WebControls.EntityDataSource-Steuerelement die Datenbindung aufruft

#### <a name="details"></a>Details

Das <xref:System.Web.UI.Page.LoadComplete>-Ereignis führt nicht mehr dazu, dass das <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName>-Steuerelement Datenbindungen für Änderungen an Erstellungs-/Update-/Löschparametern aufruft. Diese Änderung schließt unnötige Roundtrips zur Datenbank sowie ein Zurücksetzen der Werte von Steuerelementen aus und erzeugt Verhaltensweisen, die mit anderen Datensteuerelementen, z. B. <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> und <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName> konsistent sind. Diese Änderung erzeugt im unwahrscheinlichen Fall, dass Anwendungen im <xref:System.Web.UI.Page.LoadComplete>-Ereignis auf Aufrufen der Datenbindung basieren, ein anderes Verhalten.

#### <a name="suggestion"></a>Vorschlag

Wenn die Datenbindung erforderlich ist, rufen Sie sie manuell in einem Ereignis auf, das im Postback früher auftritt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
