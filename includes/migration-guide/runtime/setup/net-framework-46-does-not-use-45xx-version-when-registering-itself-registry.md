---
ms.openlocfilehash: ee5070a1a4c58d6c1282ba47c921436ca22722ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774203"
---
### <a name="the-net-framework-46-does-not-use-a-45xx-version-when-registering-itself-in-the-registry"></a><span data-ttu-id="8998f-101">.NET Framework 4.6 verwendet keine 4.5.x.x-Version bei der Registrierung</span><span class="sxs-lookup"><span data-stu-id="8998f-101">The .NET Framework 4.6 does not use a 4.5.x.x version when registering itself in the registry</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8998f-102">Details</span><span class="sxs-lookup"><span data-stu-id="8998f-102">Details</span></span>|<span data-ttu-id="8998f-103">Der Versionsschlüssel in der Registrierung (unter <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) für .NET Framework 4.6 beginnt also mit „4.6“.</span><span class="sxs-lookup"><span data-stu-id="8998f-103">As one might expect, the version key set in the registry (at <code>HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\NET Framework Setup\NDP\v4\Full</code>) for the .NET Framework 4.6 begins with '4.6', not '4.5'.</span></span> <span data-ttu-id="8998f-104">Apps, die von diesen Registrierungsschlüsseln abhängig sind, damit sie wissen, welche .NET Framework-Versionen auf dem Computer installiert sind, sollten aktualisiert werden, sodass sie Version 4.6 als mögliche Version anerkennen, die mit den 4.5.x-Vorgängerversionen kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8998f-104">Apps that depend on these registry keys to know which .NET Framework versions are installed on a machine should be updated to understand that 4.6 is a new possible version, and one that is compatible with previous 4.5.x releases.</span></span>|
|<span data-ttu-id="8998f-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8998f-105">Suggestion</span></span>|<span data-ttu-id="8998f-106">Aktualisieren Sie Apps, die über 4.5-Registrierungsschlüssel nach einer .NET Framework 4.5-Installation suchen, sodass diese auch Version 4.6 akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="8998f-106">Update apps probing for a .NET Framework 4.5 install by looking for 4.5 registry keys to also accept 4.6.</span></span>|
|<span data-ttu-id="8998f-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="8998f-107">Scope</span></span>|<span data-ttu-id="8998f-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8998f-108">Edge</span></span>|
|<span data-ttu-id="8998f-109">Version</span><span class="sxs-lookup"><span data-stu-id="8998f-109">Version</span></span>|<span data-ttu-id="8998f-110">4.6</span><span class="sxs-lookup"><span data-stu-id="8998f-110">4.6</span></span>|
|<span data-ttu-id="8998f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="8998f-111">Type</span></span>|<span data-ttu-id="8998f-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8998f-112">Runtime</span></span>|
