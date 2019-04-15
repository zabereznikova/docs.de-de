---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236733"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="85869-101">VB.NET unterstützt die Angabe partieller Namespaces für System.Windows-APIs nicht mehr</span><span class="sxs-lookup"><span data-stu-id="85869-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="85869-102">Details</span><span class="sxs-lookup"><span data-stu-id="85869-102">Details</span></span>|<span data-ttu-id="85869-103">Ab .NET Framework 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="85869-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="85869-104">Der Verweis auf <code>Windows.Forms.DialogResult</code> führt z. B. zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="85869-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="85869-105">Stattdessen muss der Code auf den vollqualifizierten Namen (<xref:System.Windows.Forms.DialogResult>) verweisen oder den bestimmten Namespace importieren und dann einfach auf <xref:System.Windows.Forms.DialogResult?displayProperty=name> verweisen.</span><span class="sxs-lookup"><span data-stu-id="85869-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="85869-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="85869-106">Suggestion</span></span>|<span data-ttu-id="85869-107">Der Code sollte aktualisiert werden, um auf <code>System.Windows</code>-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="85869-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="85869-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="85869-108">Scope</span></span>|<span data-ttu-id="85869-109">Gering</span><span class="sxs-lookup"><span data-stu-id="85869-109">Minor</span></span>|
|<span data-ttu-id="85869-110">Version</span><span class="sxs-lookup"><span data-stu-id="85869-110">Version</span></span>|<span data-ttu-id="85869-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="85869-111">4.5.2</span></span>|
|<span data-ttu-id="85869-112">Typ</span><span class="sxs-lookup"><span data-stu-id="85869-112">Type</span></span>|<span data-ttu-id="85869-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="85869-113">Retargeting</span></span>|
