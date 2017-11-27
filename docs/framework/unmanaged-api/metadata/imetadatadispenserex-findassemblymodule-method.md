---
title: IMetaDataDispenserEx::FindAssemblyModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssemblyModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3911eeb5f6ff8122c71f0c1df973c4636ad8b665
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="ed3b4-102">IMetaDataDispenserEx::FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3b4-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="ed3b4-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-103">This method is not implemented.</span></span> <span data-ttu-id="ed3b4-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3b4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed3b4-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed3b4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed3b4-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="ed3b4-107">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="ed3b4-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="ed3b4-109">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ed3b4-110">[in] Der Name des Moduls.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="ed3b4-111">[in] Die Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="ed3b4-112">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ed3b4-113">[in] Die Größe in Bytes, der `szName`.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="ed3b4-114">[out] Die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="ed3b4-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3b4-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed3b4-115">Requirements</span></span>  
 <span data-ttu-id="ed3b4-116">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3b4-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3b4-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ed3b4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed3b4-118">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ed3b4-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed3b4-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3b4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3b4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed3b4-120">See Also</span></span>  
 [<span data-ttu-id="ed3b4-121">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3b4-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="ed3b4-122">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3b4-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
