---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f7515479ae5fbe490496bac79f102b02700dcee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="dc3fb-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="dc3fb-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="dc3fb-103">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="dc3fb-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc3fb-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dc3fb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc3fb-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="dc3fb-106">[in] Die Anzahl der angeforderten Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="dc3fb-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="dc3fb-107">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="dc3fb-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="dc3fb-108">Ein Zeiger auf ein Array von [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="dc3fb-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc3fb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc3fb-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc3fb-110">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc3fb-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc3fb-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc3fb-111">Requirements</span></span>  
 <span data-ttu-id="dc3fb-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc3fb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc3fb-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc3fb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc3fb-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc3fb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc3fb-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc3fb-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3fb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc3fb-116">See Also</span></span>  
 [<span data-ttu-id="dc3fb-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc3fb-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="dc3fb-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="dc3fb-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
