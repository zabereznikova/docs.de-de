---
title: IMetaDataDispenserEx::FindAssembly-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85ebddf4ef96be2a583e54082e4d4405b30adf46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777766"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="47998-102">IMetaDataDispenserEx::FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="47998-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="47998-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="47998-103">This method is not implemented.</span></span> <span data-ttu-id="47998-104">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="47998-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47998-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47998-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="47998-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47998-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="47998-107">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="47998-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="47998-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="47998-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="47998-109">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="47998-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="47998-110">[in] Die Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="47998-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="47998-111">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="47998-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="47998-112">[in] Die Größe in Bytes, des `szName`.</span><span class="sxs-lookup"><span data-stu-id="47998-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="47998-113">[out] Die Anzahl der Zeichen im tatsächlich zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="47998-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47998-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47998-114">Requirements</span></span>  
 <span data-ttu-id="47998-115">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47998-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47998-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47998-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47998-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="47998-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47998-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47998-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47998-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47998-119">See also</span></span>

- [<span data-ttu-id="47998-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47998-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="47998-121">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47998-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
