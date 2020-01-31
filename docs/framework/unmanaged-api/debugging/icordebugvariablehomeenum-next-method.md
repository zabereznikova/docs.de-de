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
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790926"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="f5a61-102">Icordebugvariablehomeerum:: Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f5a61-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="f5a61-103">Ruft die angegebene Anzahl von [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="f5a61-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a61-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a61-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f5a61-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f5a61-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="f5a61-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="f5a61-107">Ein Array von Zeigern, von denen jedes auf ein [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekt verweist, das Informationen über eine lokale Variable oder ein Argument einer Funktion bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f5a61-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f5a61-108">vorgenommen Die Anzahl der Instanzen, die in-Objekten tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="f5a61-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a61-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f5a61-109">Return Value</span></span>  
 <span data-ttu-id="f5a61-110">Die-Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="f5a61-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="f5a61-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5a61-111">HRESULT</span></span>|<span data-ttu-id="f5a61-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5a61-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f5a61-113">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f5a61-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f5a61-114">Die tatsächliche Anzahl der abgerufenen Instanzen, die sich in `pceltFetched`widerspiegeln, ist geringer als die Anzahl der angeforderten Instanzen.</span><span class="sxs-lookup"><span data-stu-id="f5a61-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5a61-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5a61-115">Remarks</span></span>  
 <span data-ttu-id="f5a61-116">Die [icordebugvariablehomeenumeration:: Next](icordebugvariablehomeenum-next-method.md) -Methode ruft ein Maximum von `celt`-Objekten ab, beginnend an der aktuellen Position des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="f5a61-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="f5a61-117">Wenn die Methode zurückgegeben wird, enthält `pceltFetched` die tatsächliche Anzahl der abgerufenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="f5a61-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a61-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5a61-118">Requirements</span></span>  
 <span data-ttu-id="f5a61-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a61-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a61-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a61-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a61-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a61-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a61-122">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a61-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a61-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5a61-123">See also</span></span>

- [<span data-ttu-id="f5a61-124">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a61-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="f5a61-125">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a61-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
