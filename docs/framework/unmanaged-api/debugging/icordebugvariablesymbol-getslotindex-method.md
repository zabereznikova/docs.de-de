---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725988"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="d15ee-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d15ee-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="d15ee-103">Ruft den verwalteten Slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="d15ee-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d15ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d15ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d15ee-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="d15ee-106">[out] Ein Zeiger auf den Slotindex der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="d15ee-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d15ee-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d15ee-107">Return Value</span></span>  

 <span data-ttu-id="d15ee-108">Bei Erfolg `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="d15ee-108">`S_OK` if successful.</span></span> <span data-ttu-id="d15ee-109">`E_FAIL`, wenn die Variable ein Funktionsargument ist.</span><span class="sxs-lookup"><span data-stu-id="d15ee-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d15ee-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d15ee-110">Remarks</span></span>  

 <span data-ttu-id="d15ee-111">Der verwaltete Slotindex einer lokalen Variablen kann zum Abrufen der Metadateninformationen der Variablen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d15ee-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d15ee-112">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d15ee-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d15ee-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d15ee-113">Requirements</span></span>  

 <span data-ttu-id="d15ee-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d15ee-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15ee-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d15ee-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d15ee-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15ee-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15ee-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d15ee-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15ee-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d15ee-118">See also</span></span>

- [<span data-ttu-id="d15ee-119">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d15ee-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="d15ee-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d15ee-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
