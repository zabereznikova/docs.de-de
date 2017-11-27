---
title: ICorDebugDataTarget2::GetSymbolProviderForImage-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 868e1e8d670a438d7a93bfac27f213c9c35ea58c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="dedbd-102">ICorDebugDataTarget2::GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="dedbd-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="dedbd-103">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="dedbd-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dedbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dedbd-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dedbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dedbd-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="dedbd-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse eines Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="dedbd-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="dedbd-107">[out] Ein Zeiger auf die Adresse des ein [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="dedbd-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dedbd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dedbd-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dedbd-109">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dedbd-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dedbd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dedbd-110">Requirements</span></span>  
 <span data-ttu-id="dedbd-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dedbd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dedbd-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dedbd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dedbd-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dedbd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dedbd-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dedbd-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dedbd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dedbd-115">See Also</span></span>  
 [<span data-ttu-id="dedbd-116">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dedbd-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="dedbd-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="dedbd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
