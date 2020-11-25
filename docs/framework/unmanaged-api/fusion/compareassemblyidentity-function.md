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
ms.openlocfilehash: da32ce6a40378a6f88cf71bd7707be2079d71068
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717590"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="13f0d-102">CompareAssemblyIdentity-Funktion</span><span class="sxs-lookup"><span data-stu-id="13f0d-102">CompareAssemblyIdentity Function</span></span>

<span data-ttu-id="13f0d-103">Vergleicht zwei Assemblyidentitäten, um zu bestimmen, ob Sie äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="13f0d-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13f0d-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="13f0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13f0d-105">Parameters</span></span>  

 `pwzAssemblyIdentity1`  
 <span data-ttu-id="13f0d-106">in Die Text Identität der ersten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="13f0d-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="13f0d-107">in Ein boolesches Flag, das die vom Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity1` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="13f0d-108">in Die Text Identität der zweiten Assembly im Vergleich.</span><span class="sxs-lookup"><span data-stu-id="13f0d-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="13f0d-109">in Ein boolesches Flag, das die vom Benutzer angegebene Vereinheitlichung für angibt `pwzAssemblyIdentity2` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="13f0d-110">vorgenommen Ein boolesches Flag, das angibt, ob die beiden Assemblys äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="13f0d-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="13f0d-111">vorgenommen Eine [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) -Enumeration, die ausführliche Informationen über den Vergleich enthält.</span><span class="sxs-lookup"><span data-stu-id="13f0d-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13f0d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="13f0d-112">Return Value</span></span>  

 <span data-ttu-id="13f0d-113">`pfEquivalent` Gibt einen booleschen Wert zurück, der angibt, ob die beiden Assemblys äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="13f0d-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="13f0d-114">`pResult` Gibt einen der- `AssemblyComparisonResult` Werte zurück, um einen detaillierteren Grund für den Wert von zu erhalten `pfEquivalent` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13f0d-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13f0d-115">Remarks</span></span>  

 <span data-ttu-id="13f0d-116">`CompareAssemblyIdentity` überprüft, ob `pwzAssemblyIdentity1` und `pwzAssemblyIdentity2` äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="13f0d-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="13f0d-117">`pfEquivalent` wird `true` unter einer oder mehreren der folgenden Bedingungen auf festgelegt:</span><span class="sxs-lookup"><span data-stu-id="13f0d-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="13f0d-118">Die beiden Assemblyidentitäten sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="13f0d-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="13f0d-119">Für Assemblys mit starkem Namen müssen AssemblyName, Version, öffentliches Schlüssel Token und Kultur identisch sein.</span><span class="sxs-lookup"><span data-stu-id="13f0d-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="13f0d-120">Bei einfachen benannten Assemblys erfordert die Äquivalenz eine Übereinstimmung mit dem Assemblynamen und der Kultur.</span><span class="sxs-lookup"><span data-stu-id="13f0d-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="13f0d-121">Beide Assemblyidentitäten verweisen auf Assemblys, die auf dem .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="13f0d-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="13f0d-122">Diese Bedingung gibt `true` auch dann zurück, wenn die Assemblyversionsnummern nicht stimmen.</span><span class="sxs-lookup"><span data-stu-id="13f0d-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="13f0d-123">Die beiden Assemblys sind keine verwalteten Assemblys, aber `fUnified1` oder `fUnified2` wurde auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="13f0d-124">Das- `fUnified` Flag gibt an, dass alle Versionsnummern bis zur Versionsnummer der Assembly mit starkem Namen als Äquivalent zur Assembly mit starkem Namen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="13f0d-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="13f0d-125">Wenn der Wert von z. b. `pwzAssemblyIndentity1` "MyAssembly, Version = 3.0.0.0, Culture = neutral, PublicKeyToken =...." und der Wert von `fUnified1` ist `true` , gibt dies an, dass alle Versionen von myAssembly von Version 0.0.0.0 zu 3.0.0.0 als Äquivalent behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13f0d-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="13f0d-126">In einem solchen Fall, wenn `pwzAssemblyIndentity2` auf dieselbe Assembly verweist wie `pwzAssemblyIndentity1` , mit der Ausnahme, dass Sie eine niedrigere Versionsnummer aufweist, `pfEquivalent` wird auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="13f0d-127">Wenn `pwzAssemblyIdentity2` auf eine höhere Versionsnummer verweist, `pfEquivalent` wird nur auf festgelegt, `true` Wenn der Wert von auf festgelegt `fUnified2` ist `true` .</span><span class="sxs-lookup"><span data-stu-id="13f0d-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="13f0d-128">Der- `pResult` Parameter enthält spezifische Informationen darüber, warum die beiden Assemblys als gleichwertig oder nicht äquivalent angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="13f0d-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="13f0d-129">Weitere Informationen finden Sie unter [AssemblyComparisonResult-Enumeration](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="13f0d-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f0d-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13f0d-130">Requirements</span></span>  

 <span data-ttu-id="13f0d-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f0d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f0d-132">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="13f0d-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="13f0d-133">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="13f0d-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13f0d-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f0d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f0d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13f0d-135">See also</span></span>

- [<span data-ttu-id="13f0d-136">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="13f0d-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="13f0d-137">AssemblyComparisonResult-Enumeration</span><span class="sxs-lookup"><span data-stu-id="13f0d-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
