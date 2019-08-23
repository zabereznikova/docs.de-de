---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f7859b095d80edb5592af1386457ad72b85bc48
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957389"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="c6b21-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="c6b21-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="c6b21-103">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="c6b21-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6b21-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6b21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6b21-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6b21-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="c6b21-106">[in] Die Anzahl der angeforderten Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="c6b21-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="c6b21-107">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="c6b21-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="c6b21-108">Ein Zeiger auf ein Array von [icorentbugmergedassemblyrecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) -Objekten.</span><span class="sxs-lookup"><span data-stu-id="c6b21-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6b21-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6b21-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6b21-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6b21-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6b21-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6b21-111">Requirements</span></span>  
 <span data-ttu-id="c6b21-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6b21-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6b21-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c6b21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6b21-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6b21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6b21-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6b21-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6b21-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6b21-116">See also</span></span>

- [<span data-ttu-id="c6b21-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6b21-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="c6b21-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c6b21-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
