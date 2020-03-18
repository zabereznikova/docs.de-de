---
ms.openlocfilehash: c9c46793a0f66894649796d960547848ff5ebf8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858496"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridView-Steuerelemente, bei denen „AllowCustomPaging“ auf TRUE festgelegt ist, kann das Ereignis „PageIndexChanging“ ausgelöst werden, wenn die letzte Seite der Ansicht verlassen wird

|   |   |
|---|---|
|Details|Ein Fehler in .NET Framework 4.5 führt dazu, dass <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=name> für <xref:System.Web.UI.WebControls.GridView?displayProperty=name>-Steuerelemente, bei denen <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=name> nicht aktiviert ist, manchmal nicht ausgelöst wird.|
|Vorschlag|Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden. Das Problem kann umgangen werden, indem die App eine explizite BindGrid-Bindung an eine beliebige <code>Page_Load</code>-Methode durchführt, die diese Bedingungen erfüllt (<xref:System.Web.UI.WebControls.GridView?displayProperty=name> befindet sich auf der letzten Seite und Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name> unterscheidet sich von <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=name>). Alternativ kann die App geändert werden, um Paging (statt benutzerdefiniertem Paging) zuzulassen, da das Problem in diesem Szenario nicht auftritt.|
|`Scope`|Nebenversion|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
