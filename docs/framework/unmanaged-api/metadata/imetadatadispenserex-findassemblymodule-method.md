---
title: IMetaDataDispenserEx::FindAssemblyModule-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2d1d97e443be884f45187a2811ddfce106249515
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044355"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="352ef-102">IMetaDataDispenserEx::FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="352ef-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="352ef-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="352ef-103">This method is not implemented.</span></span> <span data-ttu-id="352ef-104">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="352ef-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="352ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="352ef-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="352ef-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="352ef-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="352ef-107">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="352ef-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="352ef-108">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="352ef-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="352ef-109">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="352ef-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="352ef-110">[in] Der Name des Moduls.</span><span class="sxs-lookup"><span data-stu-id="352ef-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="352ef-111">[in] Die Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="352ef-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="352ef-112">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="352ef-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="352ef-113">[in] Die Größe in Bytes, des `szName`.</span><span class="sxs-lookup"><span data-stu-id="352ef-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="352ef-114">[out] Die Anzahl der Zeichen im tatsächlich zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="352ef-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="352ef-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="352ef-115">Requirements</span></span>  
 <span data-ttu-id="352ef-116">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="352ef-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="352ef-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="352ef-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="352ef-118">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="352ef-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="352ef-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="352ef-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="352ef-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="352ef-120">See also</span></span>

- [<span data-ttu-id="352ef-121">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="352ef-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="352ef-122">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="352ef-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
