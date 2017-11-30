---
title: IMetaDataDispenserEx::FindAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a70d1e2b3636a405fe28b84c2e76dd7264df4f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="24331-102">IMetaDataDispenserEx::FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="24331-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="24331-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="24331-103">This method is not implemented.</span></span> <span data-ttu-id="24331-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24331-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24331-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="24331-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24331-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="24331-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="24331-107">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="24331-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="24331-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="24331-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="24331-109">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="24331-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="24331-110">[in] Die Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="24331-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="24331-111">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="24331-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="24331-112">[in] Die Größe in Bytes, der `szName`.</span><span class="sxs-lookup"><span data-stu-id="24331-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="24331-113">[out] Die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="24331-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24331-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24331-114">Requirements</span></span>  
 <span data-ttu-id="24331-115">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24331-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24331-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24331-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24331-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="24331-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24331-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24331-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24331-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24331-119">See Also</span></span>  
 [<span data-ttu-id="24331-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24331-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="24331-121">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24331-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
