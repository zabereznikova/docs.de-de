---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620507"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="094a3-101">XmlSchemaException legt Zeilenpositionen jetzt ordnungsgemäß fest</span><span class="sxs-lookup"><span data-stu-id="094a3-101">XmlSchemaException now sets line positions properly</span></span>

#### <a name="details"></a><span data-ttu-id="094a3-102">Details</span><span class="sxs-lookup"><span data-stu-id="094a3-102">Details</span></span>

<span data-ttu-id="094a3-103">Wenn der <xref:System.Xml.Linq.LoadOptions.SetLineInfo>-Wert an die Load-Methode übergeben wird und ein Validierungsfehler auftritt, enthalten die Eigenschaften <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> jetzt Zeileninformationen.</span><span class="sxs-lookup"><span data-stu-id="094a3-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="094a3-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="094a3-104">Suggestion</span></span>

<span data-ttu-id="094a3-105">Ausnahmebehandlungscode, der davon ausgeht, dass <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> nicht festgelegt werden, sollte aktualisiert werden, da diese Eigenschaften jetzt ordnungsgemäß festgelegt werden kann, wenn „SetLineInfo“ beim Laden von XML verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="094a3-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>

| <span data-ttu-id="094a3-106">name</span><span class="sxs-lookup"><span data-stu-id="094a3-106">Name</span></span>    | <span data-ttu-id="094a3-107">Wert</span><span class="sxs-lookup"><span data-stu-id="094a3-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="094a3-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="094a3-108">Scope</span></span>   |<span data-ttu-id="094a3-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="094a3-109">Edge</span></span>|
|<span data-ttu-id="094a3-110">Version</span><span class="sxs-lookup"><span data-stu-id="094a3-110">Version</span></span>|<span data-ttu-id="094a3-111">4.5</span><span class="sxs-lookup"><span data-stu-id="094a3-111">4.5</span></span>|
|<span data-ttu-id="094a3-112">Typ</span><span class="sxs-lookup"><span data-stu-id="094a3-112">Type</span></span>|<span data-ttu-id="094a3-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="094a3-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="094a3-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="094a3-114">Affected APIs</span></span>

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
