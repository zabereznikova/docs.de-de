---
ms.openlocfilehash: 55a26f1ab27792cbedf3f31b797f37d3f768d51a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497278"
---
### <a name="aspnet-fix-handling-of-inputattributes-and-labelattributes-for-webforms-checkbox-control"></a><span data-ttu-id="2f355-101">Behandlung von Korrekturen in ASP.NET bei InputAttributes und LabelAttributes für WebForms CheckBox-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="2f355-101">ASP.NET Fix handling of InputAttributes and LabelAttributes for WebForms CheckBox control</span></span>

#### <a name="details"></a><span data-ttu-id="2f355-102">Details</span><span class="sxs-lookup"><span data-stu-id="2f355-102">Details</span></span>

<span data-ttu-id="2f355-103">Bei Anwendungen, die .NET Framework 4.7.2 und frühere Versionen nutzen, gehen <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> und <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType>, die einem WebForms <xref:System.Web.UI.WebControls.CheckBox>-Steuerelement programmgesteuert hinzugefügt wurden, nach einem Postback verloren.</span><span class="sxs-lookup"><span data-stu-id="2f355-103">For applications that target .NET Framework 4.7.2 and earlier versions, <xref:System.Web.UI.WebControls.CheckBox.InputAttributes?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.CheckBox.LabelAttributes?displayProperty=nameWithType> that are programmatically added to a WebForms <xref:System.Web.UI.WebControls.CheckBox> control are lost after postback.</span></span> <span data-ttu-id="2f355-104">Bei Anwendungen, die .NET Framework 4.8 oder höhere Versionen verwenden, bleiben sie nach einem Postback erhalten.</span><span class="sxs-lookup"><span data-stu-id="2f355-104">For applications that target .NET Framework 4.8 or later versions, they are preserved after postback.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2f355-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2f355-105">Suggestion</span></span>

<span data-ttu-id="2f355-106">Wenn Sie bei der Wiederherstellung nach einem Postback das richtige Verhalten erzielen möchten, legen Sie <code>targetFrameworkVersion</code> auf 4.8 oder höher fest.</span><span class="sxs-lookup"><span data-stu-id="2f355-106">For the correct behavior for restoring attributes on postback, set the <code>targetFrameworkVersion</code> to 4.8 or higher.</span></span> <span data-ttu-id="2f355-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2f355-107">For example:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;system.web&gt;&#13;&#10;&lt;httpRuntime targetFramework=&quot;4.8&quot;/&gt;&#13;&#10;&lt;/system.web&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="2f355-108">Wenn Sie eine frühere oder gar keine Version angeben, wird das alte falsche Verhalten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2f355-108">Setting it lower, or not at all, preserves the old incorrect behavior.</span></span>

| <span data-ttu-id="2f355-109">name</span><span class="sxs-lookup"><span data-stu-id="2f355-109">Name</span></span>    | <span data-ttu-id="2f355-110">Wert</span><span class="sxs-lookup"><span data-stu-id="2f355-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2f355-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="2f355-111">Scope</span></span>   |<span data-ttu-id="2f355-112">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="2f355-112">Unknown</span></span>|
|<span data-ttu-id="2f355-113">Version</span><span class="sxs-lookup"><span data-stu-id="2f355-113">Version</span></span>|<span data-ttu-id="2f355-114">4.8</span><span class="sxs-lookup"><span data-stu-id="2f355-114">4.8</span></span>|
|<span data-ttu-id="2f355-115">Typ</span><span class="sxs-lookup"><span data-stu-id="2f355-115">Type</span></span>|<span data-ttu-id="2f355-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2f355-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2f355-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2f355-117">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.CheckBox?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Web.UI.WebControls.CheckBox`

-->
