---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496614"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="c7416-101">Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert</span><span class="sxs-lookup"><span data-stu-id="c7416-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="c7416-102">Details</span><span class="sxs-lookup"><span data-stu-id="c7416-102">Details</span></span>

<span data-ttu-id="c7416-103">Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.</span><span class="sxs-lookup"><span data-stu-id="c7416-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c7416-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c7416-104">Suggestion</span></span>

<span data-ttu-id="c7416-105">Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten.</span><span class="sxs-lookup"><span data-stu-id="c7416-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="c7416-106">Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c7416-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="c7416-107">name</span><span class="sxs-lookup"><span data-stu-id="c7416-107">Name</span></span>    | <span data-ttu-id="c7416-108">Wert</span><span class="sxs-lookup"><span data-stu-id="c7416-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c7416-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="c7416-109">Scope</span></span>   |<span data-ttu-id="c7416-110">Gering</span><span class="sxs-lookup"><span data-stu-id="c7416-110">Minor</span></span>|
|<span data-ttu-id="c7416-111">Version</span><span class="sxs-lookup"><span data-stu-id="c7416-111">Version</span></span>|<span data-ttu-id="c7416-112">4.5</span><span class="sxs-lookup"><span data-stu-id="c7416-112">4.5</span></span>|
|<span data-ttu-id="c7416-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c7416-113">Type</span></span>|<span data-ttu-id="c7416-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="c7416-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c7416-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c7416-115">Affected APIs</span></span>

<span data-ttu-id="c7416-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="c7416-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
