---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804677"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="71ec9-101">VB.NET unterstützt die Angabe partieller Namespaces für System.Windows-APIs nicht mehr</span><span class="sxs-lookup"><span data-stu-id="71ec9-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="71ec9-102">Details</span><span class="sxs-lookup"><span data-stu-id="71ec9-102">Details</span></span>|<span data-ttu-id="71ec9-103">Ab .NET Framework 4.5.2 können VB.NET-Projekte keine System.Windows-APIs mit teilweise qualifizierten Namespaces angeben.</span><span class="sxs-lookup"><span data-stu-id="71ec9-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="71ec9-104">Der Verweis auf <code>Windows.Forms.DialogResult</code> führt z. B. zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="71ec9-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="71ec9-105">Stattdessen muss der Code auf den vollqualifizierten Namen (<xref:System.Windows.Forms.DialogResult>) verweisen oder den bestimmten Namespace importieren und dann einfach auf <xref:System.Windows.Forms.DialogResult?displayProperty=name> verweisen.</span><span class="sxs-lookup"><span data-stu-id="71ec9-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="71ec9-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="71ec9-106">Suggestion</span></span>|<span data-ttu-id="71ec9-107">Der Code sollte aktualisiert werden, um auf <code>System.Windows</code>-APIs mit einfachen Namen (und den entsprechenden Namespace importieren) oder mit vollqualifizierten Namen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="71ec9-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="71ec9-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="71ec9-108">Scope</span></span>|<span data-ttu-id="71ec9-109">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="71ec9-109">Minor</span></span>|
|<span data-ttu-id="71ec9-110">Version</span><span class="sxs-lookup"><span data-stu-id="71ec9-110">Version</span></span>|<span data-ttu-id="71ec9-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="71ec9-111">4.5.2</span></span>|
|<span data-ttu-id="71ec9-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="71ec9-112">Type</span></span>|<span data-ttu-id="71ec9-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="71ec9-113">Retargeting</span></span>|
