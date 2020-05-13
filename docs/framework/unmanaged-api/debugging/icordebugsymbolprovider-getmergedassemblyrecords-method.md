---
title: ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: b7d26fa80a7a8ebe7b4606b914c8cd09c52df1e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379627"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="a2a28-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="a2a28-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="a2a28-103">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="a2a28-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2a28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a28-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2a28-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="a2a28-106">[in] Die Anzahl der angeforderten Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="a2a28-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="a2a28-107">[out] Ein Zeiger auf die Anzahl der von der Methode abgerufenen Symboldatensätze.</span><span class="sxs-lookup"><span data-stu-id="a2a28-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="a2a28-108">Ein Zeiger auf ein Array von [icorentbugmergedassemblyrecord](icordebugmergedassemblyrecord-interface.md) -Objekten.</span><span class="sxs-lookup"><span data-stu-id="a2a28-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a28-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2a28-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2a28-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2a28-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a28-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2a28-111">Requirements</span></span>  
 <span data-ttu-id="a2a28-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a28-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a28-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2a28-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2a28-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2a28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2a28-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a28-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a28-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a28-116">See also</span></span>

- [<span data-ttu-id="a2a28-117">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2a28-117">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a2a28-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2a28-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
