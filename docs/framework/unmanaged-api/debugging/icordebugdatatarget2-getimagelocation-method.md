---
title: ICorDebugDataTarget2::GetImageLocation-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ab24b483eba4950b02efb89949d8c97d24b2774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="67f14-102">ICorDebugDataTarget2::GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="67f14-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="67f14-103">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="67f14-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67f14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67f14-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67f14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67f14-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="67f14-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="67f14-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="67f14-107">[in] Die Anzahl der Zeichen im Puffer, die den Modulpfad erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="67f14-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="67f14-108">[out] Ein Zeiger auf die Anzahl der in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="67f14-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="67f14-109">[out] Der Pfad des Moduls.</span><span class="sxs-lookup"><span data-stu-id="67f14-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67f14-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67f14-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67f14-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="67f14-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67f14-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67f14-112">Requirements</span></span>  
 <span data-ttu-id="67f14-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67f14-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67f14-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67f14-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67f14-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67f14-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67f14-116">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67f14-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67f14-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67f14-117">See Also</span></span>  
 [<span data-ttu-id="67f14-118">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67f14-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="67f14-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="67f14-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
