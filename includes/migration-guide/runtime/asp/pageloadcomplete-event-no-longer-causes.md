---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620154"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a><span data-ttu-id="c1341-101">Das Page.LoadComplete-Ereignis führt nicht mehr dazu, dass das System.Web.UI.WebControls.EntityDataSource-Steuerelement die Datenbindung aufruft</span><span class="sxs-lookup"><span data-stu-id="c1341-101">Page.LoadComplete event no longer causes System.Web.UI.WebControls.EntityDataSource control to invoke data binding</span></span>

#### <a name="details"></a><span data-ttu-id="c1341-102">Details</span><span class="sxs-lookup"><span data-stu-id="c1341-102">Details</span></span>

<span data-ttu-id="c1341-103">Das <xref:System.Web.UI.Page.LoadComplete>-Ereignis führt nicht mehr dazu, dass das <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName>-Steuerelement Datenbindungen für Änderungen an Erstellungs-/Update-/Löschparametern aufruft.</span><span class="sxs-lookup"><span data-stu-id="c1341-103">The <xref:System.Web.UI.Page.LoadComplete> event no longer causes the <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> control to invoke data binding for changes to create/update/delete parameters.</span></span> <span data-ttu-id="c1341-104">Diese Änderung schließt unnötige Roundtrips zur Datenbank sowie ein Zurücksetzen der Werte von Steuerelementen aus und erzeugt Verhaltensweisen, die mit anderen Datensteuerelementen, z. B. <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> und <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName> konsistent sind.</span><span class="sxs-lookup"><span data-stu-id="c1341-104">This change eliminates an extraneous trip to the database, prevents the values of controls from being reset, and produces behavior that is consistent with other data controls, such as <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> and <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>.</span></span> <span data-ttu-id="c1341-105">Diese Änderung erzeugt im unwahrscheinlichen Fall, dass Anwendungen im <xref:System.Web.UI.Page.LoadComplete>-Ereignis auf Aufrufen der Datenbindung basieren, ein anderes Verhalten.</span><span class="sxs-lookup"><span data-stu-id="c1341-105">This change produces different behavior in the unlikely event that applications rely on invoking data binding in the <xref:System.Web.UI.Page.LoadComplete> event.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c1341-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c1341-106">Suggestion</span></span>

<span data-ttu-id="c1341-107">Wenn die Datenbindung erforderlich ist, rufen Sie sie manuell in einem Ereignis auf, das im Postback früher auftritt.</span><span class="sxs-lookup"><span data-stu-id="c1341-107">If there is a need for databinding, manually invoke databind in an event that is earlier in the post-back.</span></span>

| <span data-ttu-id="c1341-108">name</span><span class="sxs-lookup"><span data-stu-id="c1341-108">Name</span></span>    | <span data-ttu-id="c1341-109">Wert</span><span class="sxs-lookup"><span data-stu-id="c1341-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c1341-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="c1341-110">Scope</span></span>   |<span data-ttu-id="c1341-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c1341-111">Edge</span></span>|
|<span data-ttu-id="c1341-112">Version</span><span class="sxs-lookup"><span data-stu-id="c1341-112">Version</span></span>|<span data-ttu-id="c1341-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c1341-113">4.5</span></span>|
|<span data-ttu-id="c1341-114">Typ</span><span class="sxs-lookup"><span data-stu-id="c1341-114">Type</span></span>|<span data-ttu-id="c1341-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c1341-115">Runtime</span></span>|
