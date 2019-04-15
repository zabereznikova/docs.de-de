---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235770"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="2b033-101">Verwaltete Browser-Hoststeuerelemente von .NET Framework 1.1 und 2.0 werden blockiert</span><span class="sxs-lookup"><span data-stu-id="2b033-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2b033-102">Details</span><span class="sxs-lookup"><span data-stu-id="2b033-102">Details</span></span>|<span data-ttu-id="2b033-103">Das Hosting dieser Steuerelemente wird in Internet Explorer blockiert.</span><span class="sxs-lookup"><span data-stu-id="2b033-103">Hosting these controls is blocked in Internet Explorer.</span></span>|
|<span data-ttu-id="2b033-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2b033-104">Suggestion</span></span>|<span data-ttu-id="2b033-105">Internet Explorer kann eine Anwendung, die verwaltete Browserhostingsteuerelemente verwendet, nicht starten.</span><span class="sxs-lookup"><span data-stu-id="2b033-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="2b033-106">Das vorherige Verhalten kann wiederhergestellt werden, indem der EnableIEHosting-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> für x86-Systeme und für 32-Bit-Prozesse auf x64-Systeme auf <code>1</code> festgelegt wird und indem der <code>EnableIEHosting</code>-Wert des Registrierungsunterschlüssels <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> für 64-Bit-Prozesse auf x64-Systemen auf <code>1</code> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2b033-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>|
|<span data-ttu-id="2b033-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="2b033-107">Scope</span></span>|<span data-ttu-id="2b033-108">Gering</span><span class="sxs-lookup"><span data-stu-id="2b033-108">Minor</span></span>|
|<span data-ttu-id="2b033-109">Version</span><span class="sxs-lookup"><span data-stu-id="2b033-109">Version</span></span>|<span data-ttu-id="2b033-110">4.5</span><span class="sxs-lookup"><span data-stu-id="2b033-110">4.5</span></span>|
|<span data-ttu-id="2b033-111">Typ</span><span class="sxs-lookup"><span data-stu-id="2b033-111">Type</span></span>|<span data-ttu-id="2b033-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2b033-112">Runtime</span></span>|
