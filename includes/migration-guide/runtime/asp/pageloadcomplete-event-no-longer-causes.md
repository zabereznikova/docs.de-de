---
ms.openlocfilehash: 02a3c1b5a9693535feeab56d9b0f7c9d360749ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235730"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>Das Page.LoadComplete-Ereignis führt nicht mehr dazu, dass das System.Web.UI.WebControls.EntityDataSource-Steuerelement die Datenbindung aufruft

|   |   |
|---|---|
|Details|Das <xref:System.Web.UI.Page.LoadComplete>-Ereignis führt nicht mehr dazu, dass das <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=name>-Steuerelement Datenbindungen für Änderungen an Erstellungs-/Update-/Löschparametern aufruft. Diese Änderung schließt unnötige Roundtrips zur Datenbank sowie ein Zurücksetzen der Werte von Steuerelementen aus und erzeugt Verhaltensweisen, die mit anderen Datensteuerelementen, z. B. <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=name> und <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=name> konsistent sind. Diese Änderung erzeugt im unwahrscheinlichen Fall, dass Anwendungen im <xref:System.Web.UI.Page.LoadComplete>-Ereignis auf Aufrufen der Datenbindung basieren, ein anderes Verhalten.|
|Vorschlag|Wenn die Datenbindung erforderlich ist, rufen Sie sie manuell in einem Ereignis auf, das im Postback früher auftritt.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
