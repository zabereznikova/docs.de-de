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
ms.openlocfilehash: 2d974b7368dd01062d2d310d076dce05e102eb81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442291"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="3a1ee-102">IMetaDataDispenserEx::FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="3a1ee-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="3a1ee-103">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-103">This method is not implemented.</span></span> <span data-ttu-id="3a1ee-104">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1ee-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a1ee-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3a1ee-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a1ee-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="3a1ee-107">in Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="3a1ee-108">in Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="3a1ee-109">in Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="3a1ee-110">in Die Assembly, die gefunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="3a1ee-111">vorgenommen Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3a1ee-112">in Die Größe `szName`in Byte.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="3a1ee-113">vorgenommen Die Anzahl der Zeichen, die tatsächlich in `szName`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a1ee-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3a1ee-114">Requirements</span></span>  
 <span data-ttu-id="3a1ee-115">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a1ee-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a1ee-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a1ee-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a1ee-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a1ee-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a1ee-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a1ee-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1ee-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a1ee-119">See also</span></span>

- [<span data-ttu-id="3a1ee-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a1ee-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="3a1ee-121">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a1ee-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
