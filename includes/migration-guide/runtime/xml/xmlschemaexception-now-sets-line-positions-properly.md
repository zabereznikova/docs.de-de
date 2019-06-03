---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379603"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a><span data-ttu-id="ef510-101">XmlSchemaException legt Zeilenpositionen jetzt ordnungsgemäß fest</span><span class="sxs-lookup"><span data-stu-id="ef510-101">XmlSchemaException now sets line positions properly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ef510-102">Details</span><span class="sxs-lookup"><span data-stu-id="ef510-102">Details</span></span>|<span data-ttu-id="ef510-103">Wenn der <xref:System.Xml.Linq.LoadOptions.SetLineInfo>-Wert an die Load-Methode übergeben wird und ein Validierungsfehler auftritt, enthalten die Eigenschaften <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> jetzt Zeileninformationen.</span><span class="sxs-lookup"><span data-stu-id="ef510-103">If the <xref:System.Xml.Linq.LoadOptions.SetLineInfo> value is passed to the Load method and a validation error occurs, the <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> properties now contain line information.</span></span>|
|<span data-ttu-id="ef510-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ef510-104">Suggestion</span></span>|<span data-ttu-id="ef510-105">Ausnahmebehandlungscode, der davon ausgeht, dass <xref:System.Xml.Schema.XmlSchemaException.LineNumber> und <xref:System.Xml.Schema.XmlSchemaException.LinePosition> nicht festgelegt werden, sollte aktualisiert werden, da diese Eigenschaften jetzt ordnungsgemäß festgelegt werden kann, wenn „SetLineInfo“ beim Laden von XML verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ef510-105">Exception-handling code that assumes <xref:System.Xml.Schema.XmlSchemaException.LineNumber> and <xref:System.Xml.Schema.XmlSchemaException.LinePosition> will not be set should be updated since these properties will now be set properly when SetLineInfo is used while loading XML.</span></span>|
|<span data-ttu-id="ef510-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="ef510-106">Scope</span></span>|<span data-ttu-id="ef510-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ef510-107">Edge</span></span>|
|<span data-ttu-id="ef510-108">Version</span><span class="sxs-lookup"><span data-stu-id="ef510-108">Version</span></span>|<span data-ttu-id="ef510-109">4.5</span><span class="sxs-lookup"><span data-stu-id="ef510-109">4.5</span></span>|
|<span data-ttu-id="ef510-110">Typ</span><span class="sxs-lookup"><span data-stu-id="ef510-110">Type</span></span>|<span data-ttu-id="ef510-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ef510-111">Runtime</span></span>|
|<span data-ttu-id="ef510-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ef510-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
