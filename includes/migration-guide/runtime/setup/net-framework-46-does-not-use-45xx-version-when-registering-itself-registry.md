---
ms.openlocfilehash: 09fb7a54fccd5cf37800483c64e2fa6a54681f11
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621329"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="b1a12-101">.NET Framework 4.6 verwendet keine 4.5.x.x-Version bei der Registrierung</span><span class="sxs-lookup"><span data-stu-id="b1a12-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

#### <a name="details"></a><span data-ttu-id="b1a12-102">Details</span><span class="sxs-lookup"><span data-stu-id="b1a12-102">Details</span></span>

<span data-ttu-id="b1a12-103">Der Versionsschlüssel in der Registrierung (unter <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) für .NET Framework 4.6 beginnt also mit „4.6“.</span><span class="sxs-lookup"><span data-stu-id="b1a12-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="b1a12-104">Apps, die von diesen Registrierungsschlüsseln abhängig sind, damit sie wissen, welche .NET Framework-Versionen auf dem Computer installiert sind, sollten aktualisiert werden, sodass sie Version 4.6 als mögliche Version anerkennen, die mit den 4.5.x-Vorgängerversionen kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b1a12-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b1a12-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b1a12-105">Suggestion</span></span>

<span data-ttu-id="b1a12-106">Aktualisieren Sie Apps, die über 4.5-Registrierungsschlüssel nach einer .NET Framework 4.5-Installation suchen, sodass diese auch Version 4.6 akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b1a12-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>

| <span data-ttu-id="b1a12-107">name</span><span class="sxs-lookup"><span data-stu-id="b1a12-107">Name</span></span>    | <span data-ttu-id="b1a12-108">Wert</span><span class="sxs-lookup"><span data-stu-id="b1a12-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b1a12-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="b1a12-109">Scope</span></span>   |<span data-ttu-id="b1a12-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b1a12-110">Edge</span></span>|
|<span data-ttu-id="b1a12-111">Version</span><span class="sxs-lookup"><span data-stu-id="b1a12-111">Version</span></span>|<span data-ttu-id="b1a12-112">4.6</span><span class="sxs-lookup"><span data-stu-id="b1a12-112">4.6</span></span>|
|<span data-ttu-id="b1a12-113">Typ</span><span class="sxs-lookup"><span data-stu-id="b1a12-113">Type</span></span>|<span data-ttu-id="b1a12-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b1a12-114">Runtime</span></span>|
