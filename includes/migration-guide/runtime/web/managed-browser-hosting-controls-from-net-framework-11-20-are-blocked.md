---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620402"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="700f9-101">Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert</span><span class="sxs-lookup"><span data-stu-id="700f9-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="700f9-102">Details</span><span class="sxs-lookup"><span data-stu-id="700f9-102">Details</span></span>

<span data-ttu-id="700f9-103">Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.</span><span class="sxs-lookup"><span data-stu-id="700f9-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="700f9-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="700f9-104">Suggestion</span></span>

<span data-ttu-id="700f9-105">Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten.</span><span class="sxs-lookup"><span data-stu-id="700f9-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="700f9-106">Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="700f9-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="700f9-107">name</span><span class="sxs-lookup"><span data-stu-id="700f9-107">Name</span></span>    | <span data-ttu-id="700f9-108">Wert</span><span class="sxs-lookup"><span data-stu-id="700f9-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="700f9-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="700f9-109">Scope</span></span>   |<span data-ttu-id="700f9-110">Gering</span><span class="sxs-lookup"><span data-stu-id="700f9-110">Minor</span></span>|
|<span data-ttu-id="700f9-111">Version</span><span class="sxs-lookup"><span data-stu-id="700f9-111">Version</span></span>|<span data-ttu-id="700f9-112">4.5</span><span class="sxs-lookup"><span data-stu-id="700f9-112">4.5</span></span>|
|<span data-ttu-id="700f9-113">Typ</span><span class="sxs-lookup"><span data-stu-id="700f9-113">Type</span></span>|<span data-ttu-id="700f9-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="700f9-114">Runtime</span></span>|
