---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496715"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a>GridView-Steuerelemente, bei denen „AllowCustomPaging“ auf TRUE festgelegt ist, kann das Ereignis „PageIndexChanging“ ausgelöst werden, wenn die letzte Seite der Ansicht verlassen wird

#### <a name="details"></a>Details

Ein Fehler in .NET Framework 4.5 führt dazu, dass <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> für <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>-Steuerelemente, bei denen <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> nicht aktiviert ist, manchmal nicht ausgelöst wird.

#### <a name="suggestion"></a>Vorschlag

Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden. Das Problem kann umgangen werden, indem die App eine explizite BindGrid-Bindung an eine beliebige <code>Page_Load</code>-Methode durchführt, die diese Bedingungen erfüllt (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> befindet sich auf der letzten Seite und Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> unterscheidet sich von <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>). Alternativ kann die App geändert werden, um Paging (statt benutzerdefiniertem Paging) zuzulassen, da das Problem in diesem Szenario nicht auftritt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
