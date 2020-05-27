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
ms.openlocfilehash: 64f1e2a8f05616c7ca84bc130428629b1176e985
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006180"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="fbae3-102">IMetaDataDispenserEx::FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="fbae3-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="fbae3-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="fbae3-103">This method is not implemented.</span></span> <span data-ttu-id="fbae3-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbae3-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbae3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbae3-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="fbae3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbae3-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="fbae3-107">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbae3-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="fbae3-108">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbae3-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="fbae3-109">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbae3-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="fbae3-110">in Der Name des Moduls.</span><span class="sxs-lookup"><span data-stu-id="fbae3-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="fbae3-111">in Die Assembly, die gefunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="fbae3-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="fbae3-112">vorgenommen Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="fbae3-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fbae3-113">in Die Größe von in Bytes `szName` .</span><span class="sxs-lookup"><span data-stu-id="fbae3-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="fbae3-114">vorgenommen Die Anzahl der Zeichen, die tatsächlich in zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="fbae3-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbae3-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fbae3-115">Requirements</span></span>  
 <span data-ttu-id="fbae3-116">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbae3-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbae3-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fbae3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbae3-118">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="fbae3-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fbae3-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbae3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbae3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbae3-120">See also</span></span>

- [<span data-ttu-id="fbae3-121">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbae3-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="fbae3-122">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbae3-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
