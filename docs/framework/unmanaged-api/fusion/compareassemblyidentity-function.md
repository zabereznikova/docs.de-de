---
title: CompareAssemblyIdentity-Funktion
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 652000367c19572f73296c704047830ce1c74574
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231037"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="22fd9-102">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="22fd9-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="22fd9-103">Vergleicht zwei Assemblyidentitäten aus, um festzustellen, ob sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="22fd9-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22fd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22fd9-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="22fd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22fd9-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="22fd9-106">[in] Die Text Identität der ersten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="22fd9-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="22fd9-107">[in] Ein boolesches Flag zur Angabe von benutzerdefinierten Vereinheitlichung für `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="22fd9-108">[in] Die Text Identität der zweiten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="22fd9-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="22fd9-109">[in] Ein boolesches Flag zur Angabe von benutzerdefinierten Vereinheitlichung für `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="22fd9-110">[out] Ein boolesches Flag, der angibt, ob die beiden Assemblys identisch sind.</span><span class="sxs-lookup"><span data-stu-id="22fd9-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="22fd9-111">[out] Ein [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen über den Vergleich enthält.</span><span class="sxs-lookup"><span data-stu-id="22fd9-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22fd9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22fd9-112">Return Value</span></span>  
 `pfEquivalent` <span data-ttu-id="22fd9-113">Gibt einen booleschen Wert, der angibt, ob die beiden Assemblys identisch sind.</span><span class="sxs-lookup"><span data-stu-id="22fd9-113">returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> `pResult` <span data-ttu-id="22fd9-114">Gibt einen von der `AssemblyComparisonResult` Werte und geben Sie einen ausführlicheren Grund für den Wert des `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-114">returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22fd9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22fd9-115">Remarks</span></span>  
 `CompareAssemblyIdentity` <span data-ttu-id="22fd9-116">überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="22fd9-116">checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> `pfEquivalent` <span data-ttu-id="22fd9-117">nastaven NA hodnotu `true` unter eine oder mehrere der folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="22fd9-117">is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="22fd9-118">Die zwei Assemblyidentitäten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="22fd9-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="22fd9-119">Für Assemblys mit starkem Namen erfordert die Äquivalenz der Assemblyname, Version, Token des öffentlichen Schlüssels und Kultur identisch sein.</span><span class="sxs-lookup"><span data-stu-id="22fd9-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="22fd9-120">Für Assemblys mit einfachen Namen erfordert die Äquivalenz eine Übereinstimmung bei den Assemblynamen und Kultur.</span><span class="sxs-lookup"><span data-stu-id="22fd9-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="22fd9-121">Beide Assemblyidentitäten verweisen auf Assemblys, die auf .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="22fd9-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="22fd9-122">Diese Bedingung gibt `true` , auch wenn die Versionsnummern der Assembly nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="22fd9-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="22fd9-123">Die beiden Assemblys sind nicht verwaltete Assemblys, aber `fUnified1` oder `fUnified2` wurde `true`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="22fd9-124">Die `fUnified` Flag gibt an, dass alle Versionsnummern bis zu die Versionsnummer der Assembly mit starkem Namen entspricht, auf die Assembly mit starkem Namen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="22fd9-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="22fd9-125">Z. B. wenn der Wert des `pwzAssemblyIndentity1` ist "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =...", und der Wert der `fUnified1` ist `true`, dies weist darauf hin, dass alle Versionen von MyAssembly, Version "0.0.0.0" bis 3.0.0.0 sein soll als gleichwertig behandelt.</span><span class="sxs-lookup"><span data-stu-id="22fd9-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="22fd9-126">In diesem Fall wenn `pwzAssemblyIndentity2` bezieht sich auf der gleichen Assembly wie `pwzAssemblyIndentity1`, außer dass es auf eine niedrigere Versionsnummer wurde `pfEquivalent` nastaven NA hodnotu `true`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="22fd9-127">Wenn `pwzAssemblyIdentity2` bezieht sich auf eine höhere Versionsnummer `pfEquivalent` nastaven NA hodnotu `true` nur, wenn der Wert des `fUnified2` ist `true`.</span><span class="sxs-lookup"><span data-stu-id="22fd9-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="22fd9-128">Die `pResult` Parameter enthält spezielle Informationen, warum die zwei Assemblys als äquivalent betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="22fd9-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="22fd9-129">Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="22fd9-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22fd9-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22fd9-130">Requirements</span></span>  
 <span data-ttu-id="22fd9-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22fd9-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22fd9-132">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="22fd9-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="22fd9-133">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="22fd9-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="22fd9-134">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="22fd9-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="22fd9-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22fd9-135">See also</span></span>

- [<span data-ttu-id="22fd9-136">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="22fd9-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="22fd9-137">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="22fd9-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
