---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1657ed4d8326b573fe081b98c1fc414e231ac465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420621"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="01bfd-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="01bfd-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="01bfd-103">Ruft den verwalteten Slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="01bfd-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01bfd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01bfd-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01bfd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01bfd-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="01bfd-106">[out] Ein Zeiger auf den Slotindex der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="01bfd-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01bfd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="01bfd-107">Return Value</span></span>  
 <span data-ttu-id="01bfd-108">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="01bfd-108">`S_OK` if successful.</span></span> <span data-ttu-id="01bfd-109">`E_FAIL`, wenn die Variable ein Funktionsargument ist.</span><span class="sxs-lookup"><span data-stu-id="01bfd-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01bfd-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01bfd-110">Remarks</span></span>  
 <span data-ttu-id="01bfd-111">Der verwaltete Slotindex einer lokalen Variablen kann zum Abrufen der Metadateninformationen der Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01bfd-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01bfd-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01bfd-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01bfd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01bfd-113">Requirements</span></span>  
 <span data-ttu-id="01bfd-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01bfd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01bfd-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01bfd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01bfd-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01bfd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01bfd-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01bfd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01bfd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01bfd-118">See Also</span></span>  
 [<span data-ttu-id="01bfd-119">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01bfd-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="01bfd-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01bfd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
