---
ms.openlocfilehash: 424e8ff704b888aa3d2c1254ac712da4034f59b8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616114"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="54b87-101">ObsoleteAttribute wird in WinMD-Szenarios sowohl als ObsoleteAttribute als auch als DeprecatedAttribute exportiert</span><span class="sxs-lookup"><span data-stu-id="54b87-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

#### <a name="details"></a><span data-ttu-id="54b87-102">Details</span><span class="sxs-lookup"><span data-stu-id="54b87-102">Details</span></span>

<span data-ttu-id="54b87-103">Wenn Sie eine Windows-Metadatenbibliothek (WINMD-Datei) erstellen, wird das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> als <xref:System.ObsoleteAttribute?displayProperty=fullName> und als [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) exportiert.</span><span class="sxs-lookup"><span data-stu-id="54b87-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="54b87-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="54b87-104">Suggestion</span></span>

<span data-ttu-id="54b87-105">Durch die Neukompilierung von vorhandenem Quellcode, in dem das Attribut <xref:System.ObsoleteAttribute?displayProperty=fullName> verwendet wird, können Warnungen generiert werden, wenn dieser Code von C++/CX oder JavaScript verarbeitet wird. Es wird davon abgeraten, sowohl <xref:System.ObsoleteAttribute?displayProperty=fullName> als auch [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) in Code in verwalteten Assemblys anzuwenden, da dies zu Buildwarnungen führen kann.</span><span class="sxs-lookup"><span data-stu-id="54b87-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=fullName> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=fullName> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>

| <span data-ttu-id="54b87-106">name</span><span class="sxs-lookup"><span data-stu-id="54b87-106">Name</span></span>    | <span data-ttu-id="54b87-107">Wert</span><span class="sxs-lookup"><span data-stu-id="54b87-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="54b87-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="54b87-108">Scope</span></span>   | <span data-ttu-id="54b87-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="54b87-109">Edge</span></span>        |
| <span data-ttu-id="54b87-110">Version</span><span class="sxs-lookup"><span data-stu-id="54b87-110">Version</span></span> | <span data-ttu-id="54b87-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="54b87-111">4.5.1</span></span>       |
| <span data-ttu-id="54b87-112">Typ</span><span class="sxs-lookup"><span data-stu-id="54b87-112">Type</span></span>    | <span data-ttu-id="54b87-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="54b87-113">Retargeting</span></span> |
