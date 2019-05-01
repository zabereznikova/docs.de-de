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
ms.openlocfilehash: d204ec29304fe0c4596950cd17c48d0c1d2ac616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050154"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="51978-102">IMetaDataDispenserEx::FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="51978-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="51978-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="51978-103">This method is not implemented.</span></span> <span data-ttu-id="51978-104">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="51978-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51978-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51978-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="51978-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51978-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="51978-107">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="51978-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="51978-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="51978-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="51978-109">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="51978-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="51978-110">[in] Die Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="51978-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="51978-111">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="51978-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="51978-112">[in] Die Größe in Bytes, des `szName`.</span><span class="sxs-lookup"><span data-stu-id="51978-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="51978-113">[out] Die Anzahl der Zeichen im tatsächlich zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="51978-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51978-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51978-114">Requirements</span></span>  
 <span data-ttu-id="51978-115">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51978-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51978-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51978-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51978-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="51978-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51978-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51978-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51978-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51978-119">See also</span></span>

- [<span data-ttu-id="51978-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51978-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="51978-121">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51978-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
