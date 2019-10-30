---
title: 'Icordebugvariablehomeerum:: Next-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 9c2c16789fb61099c9b7c58154810739d225af1f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121919"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="d75f2-102">Icordebugvariablehomeerum:: Next-Methode</span><span class="sxs-lookup"><span data-stu-id="d75f2-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="d75f2-103">Ruft die angegebene Anzahl von [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="d75f2-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d75f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d75f2-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d75f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d75f2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d75f2-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="d75f2-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="d75f2-107">Ein Array von Zeigern, von denen jedes auf ein [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekt verweist, das Informationen über eine lokale Variable oder ein Argument einer Funktion bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d75f2-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d75f2-108">vorgenommen Die Anzahl der Instanzen, die in-Objekten tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="d75f2-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d75f2-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d75f2-109">Return Value</span></span>  
 <span data-ttu-id="d75f2-110">Die-Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="d75f2-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="d75f2-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d75f2-111">HRESULT</span></span>|<span data-ttu-id="d75f2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d75f2-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d75f2-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d75f2-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d75f2-114">Die tatsächliche Anzahl der abgerufenen Instanzen, die sich in `pceltFetched`widerspiegeln, ist geringer als die Anzahl der angeforderten Instanzen.</span><span class="sxs-lookup"><span data-stu-id="d75f2-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d75f2-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d75f2-115">Remarks</span></span>  
 <span data-ttu-id="d75f2-116">Die [icordebugvariablehomeenumeration:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) -Methode ruft ein Maximum von `celt`-Objekten ab, beginnend an der aktuellen Position des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="d75f2-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="d75f2-117">Wenn die Methode zurückgegeben wird, enthält `pceltFetched` die tatsächliche Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="d75f2-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d75f2-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d75f2-118">Requirements</span></span>  
 <span data-ttu-id="d75f2-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d75f2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d75f2-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d75f2-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d75f2-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d75f2-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d75f2-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d75f2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75f2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d75f2-123">See also</span></span>

- [<span data-ttu-id="d75f2-124">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d75f2-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="d75f2-125">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d75f2-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
