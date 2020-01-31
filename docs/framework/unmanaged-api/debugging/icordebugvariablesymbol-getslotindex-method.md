---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790894"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="b361f-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b361f-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="b361f-103">Ruft den verwalteten Slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="b361f-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b361f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b361f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b361f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b361f-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="b361f-106">[out] Ein Zeiger auf den Slotindex der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="b361f-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b361f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b361f-107">Return Value</span></span>  
 <span data-ttu-id="b361f-108">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="b361f-108">`S_OK` if successful.</span></span> <span data-ttu-id="b361f-109">`E_FAIL`, wenn die Variable ein Funktionsargument ist.</span><span class="sxs-lookup"><span data-stu-id="b361f-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b361f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b361f-110">Remarks</span></span>  
 <span data-ttu-id="b361f-111">Der verwaltete Slotindex einer lokalen Variablen kann zum Abrufen der Metadateninformationen der Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b361f-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b361f-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b361f-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b361f-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b361f-113">Requirements</span></span>  
 <span data-ttu-id="b361f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b361f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b361f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b361f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b361f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b361f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b361f-117">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b361f-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b361f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b361f-118">See also</span></span>

- [<span data-ttu-id="b361f-119">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b361f-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="b361f-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b361f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
