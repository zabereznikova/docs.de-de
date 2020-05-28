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
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006193"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="92d52-102">IMetaDataDispenserEx::FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="92d52-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="92d52-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="92d52-103">This method is not implemented.</span></span> <span data-ttu-id="92d52-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="92d52-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92d52-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="92d52-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="92d52-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="92d52-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="92d52-107">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="92d52-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="92d52-108">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="92d52-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="92d52-109">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="92d52-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="92d52-110">in Die Assembly, die gefunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="92d52-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="92d52-111">vorgenommen Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="92d52-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="92d52-112">in Die Größe von in Bytes `szName` .</span><span class="sxs-lookup"><span data-stu-id="92d52-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="92d52-113">vorgenommen Die Anzahl der Zeichen, die tatsächlich in zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="92d52-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92d52-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="92d52-114">Requirements</span></span>  
 <span data-ttu-id="92d52-115">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92d52-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92d52-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="92d52-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92d52-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="92d52-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92d52-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92d52-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92d52-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92d52-119">See also</span></span>

- [<span data-ttu-id="92d52-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92d52-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="92d52-121">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92d52-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
