---
title: CompareAssemblyIdentity-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: CompareAssemblyIdentity
helpviewer_keywords: CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d9d7b4934d4295ee799fb13d3d749e6b977e644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="b84a5-102">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="b84a5-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="b84a5-103">Vergleicht zwei Assemblyidentitäten, um zu bestimmen, ob sie gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b84a5-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b84a5-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b84a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b84a5-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="b84a5-106">[in] Die textbasierten Identität der ersten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="b84a5-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="b84a5-107">[in] Ein boolesches Flag, das Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="b84a5-108">[in] Die textbasierten Identität der zweiten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="b84a5-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="b84a5-109">[in] Ein boolesches Flag, das Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="b84a5-110">[out] Ein boolesches Flag, der angibt, ob die beiden Assemblys identisch sind.</span><span class="sxs-lookup"><span data-stu-id="b84a5-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="b84a5-111">[out] Ein [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen zum Vergleich bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b84a5-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b84a5-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b84a5-112">Return Value</span></span>  
 <span data-ttu-id="b84a5-113">`pfEquivalent`Gibt einen booleschen Wert, der angibt, ob die beiden Assemblys identisch sind.</span><span class="sxs-lookup"><span data-stu-id="b84a5-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="b84a5-114">`pResult`Gibt einen von der `AssemblyComparisonResult` -Werten, um eine detailliertere Begründung für den Wert des `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b84a5-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b84a5-115">Remarks</span></span>  
 <span data-ttu-id="b84a5-116">`CompareAssemblyIdentity`überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="b84a5-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="b84a5-117">`pfEquivalent`-Wert von `true` unter einer oder mehreren der folgenden Bedingungen:</span><span class="sxs-lookup"><span data-stu-id="b84a5-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="b84a5-118">Die zwei Assemblyidentitäten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b84a5-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="b84a5-119">Für Assemblys mit starkem Namen erfordert Äquivalenz Assemblyname, Version, öffentliches Schlüsseltoken und Kultur identisch sein.</span><span class="sxs-lookup"><span data-stu-id="b84a5-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="b84a5-120">Für Assemblys mit einfachen Namen erfordert Äquivalenz eine Übereinstimmung bei der Assemblyname und Kultur entspricht.</span><span class="sxs-lookup"><span data-stu-id="b84a5-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="b84a5-121">Beide Assemblyidentitäten verweisen auf Assemblys, die auf .NET Framework ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b84a5-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="b84a5-122">Diese Bedingung gibt `true` , selbst wenn die Assemblyversionsnummern nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b84a5-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="b84a5-123">Die beiden Assemblys sind nicht verwaltete Assemblys, aber `fUnified1` oder `fUnified2` wurde `true`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="b84a5-124">Die `fUnified` Flag gibt an, dass alle Versionsnummern bis zu die Versionsnummer der Assembly mit starkem Namen als auf die Assembly mit starkem Namen gleichwertig betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="b84a5-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="b84a5-125">Z. B. wenn der Wert der `pwzAssemblyIndentity1` ist "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =...", und der Wert des `fUnified1` ist `true`, dies gibt an, dass alle Versionen von MyAssembly von Version 0.0.0.0 bis 3.0.0.0 werden soll als Äquivalent behandelt.</span><span class="sxs-lookup"><span data-stu-id="b84a5-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="b84a5-126">In diesem Fall wenn `pwzAssemblyIndentity2` bezieht sich auf derselben Assembly wie `pwzAssemblyIndentity1`, außer dass es eine niedrigere Versionsnummer hat `pfEquivalent` auf festgelegt ist `true`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="b84a5-127">Wenn `pwzAssemblyIdentity2` bezieht sich auf eine höhere Versionsnummer `pfEquivalent` festgelegt ist, um `true` nur, wenn der Wert der `fUnified2` ist `true`.</span><span class="sxs-lookup"><span data-stu-id="b84a5-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="b84a5-128">Die `pResult` Parameter enthält bestimmte Informationen, warum die zwei Assemblys als äquivalent betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="b84a5-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="b84a5-129">Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b84a5-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b84a5-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b84a5-130">Requirements</span></span>  
 <span data-ttu-id="b84a5-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b84a5-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b84a5-132">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b84a5-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b84a5-133">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b84a5-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b84a5-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b84a5-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84a5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b84a5-135">See Also</span></span>  
 [<span data-ttu-id="b84a5-136">Globale statische Fusionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b84a5-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="b84a5-137">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b84a5-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
