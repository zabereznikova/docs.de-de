---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616059"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="d1308-101">VB.NET unterstützt die Angabe partieller Namespaces für System.Windows-APIs nicht mehr</span><span class="sxs-lookup"><span data-stu-id="d1308-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="d1308-102">Details</span><span class="sxs-lookup"><span data-stu-id="d1308-102">Details</span></span>

<span data-ttu-id="d1308-103">Ab .NET Framework 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="d1308-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="d1308-104">Der Verweis auf `Windows.Forms.DialogResult` führt z. B. zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="d1308-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="d1308-105">Stattdessen muss der Code auf den vollqualifizierten Namen (<xref:System.Windows.Forms.DialogResult>) verweisen oder den bestimmten Namespace importieren und dann einfach auf <xref:System.Windows.Forms.DialogResult?displayProperty=fullName> verweisen.</span><span class="sxs-lookup"><span data-stu-id="d1308-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d1308-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d1308-106">Suggestion</span></span>

<span data-ttu-id="d1308-107">Der Code sollte aktualisiert werden, um auf `System.Windows`-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d1308-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="d1308-108">name</span><span class="sxs-lookup"><span data-stu-id="d1308-108">Name</span></span>    | <span data-ttu-id="d1308-109">Wert</span><span class="sxs-lookup"><span data-stu-id="d1308-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d1308-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="d1308-110">Scope</span></span>   | <span data-ttu-id="d1308-111">Gering</span><span class="sxs-lookup"><span data-stu-id="d1308-111">Minor</span></span>       |
| <span data-ttu-id="d1308-112">Version</span><span class="sxs-lookup"><span data-stu-id="d1308-112">Version</span></span> | <span data-ttu-id="d1308-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="d1308-113">4.5.2</span></span>       |
| <span data-ttu-id="d1308-114">Typ</span><span class="sxs-lookup"><span data-stu-id="d1308-114">Type</span></span>    | <span data-ttu-id="d1308-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d1308-115">Retargeting</span></span> |
