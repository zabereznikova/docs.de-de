---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 502e7e0b52bb147b5fe37dcc6e4f6d13d642b6f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417543"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="7943d-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="7943d-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="7943d-103">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="7943d-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7943d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7943d-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7943d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7943d-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="7943d-106">[in] Die Anzahl der angeforderten Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="7943d-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="7943d-107">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="7943d-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="7943d-108">Ein Zeiger auf ein Array von [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="7943d-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7943d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7943d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7943d-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7943d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7943d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7943d-111">Requirements</span></span>  
 <span data-ttu-id="7943d-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7943d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7943d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7943d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7943d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7943d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7943d-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7943d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7943d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7943d-116">See Also</span></span>  
 [<span data-ttu-id="7943d-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7943d-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="7943d-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7943d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
