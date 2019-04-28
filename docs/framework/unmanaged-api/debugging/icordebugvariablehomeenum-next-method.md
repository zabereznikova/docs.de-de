---
title: ICorDebugVariableHomeEnum::Next-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be1ba87ae979911dd21647569725eafa2c80ffa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768809"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="aacdd-102">ICorDebugVariableHomeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="aacdd-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="aacdd-103">Ruft die angegebene Anzahl von [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanzen, die Informationen über die lokalen Variablen und Argumente in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="aacdd-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aacdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aacdd-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aacdd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aacdd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="aacdd-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="aacdd-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="aacdd-107">Ein Array von Zeigern, die jeweils auf eine [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekt, das Informationen über eine lokale Variable oder ein Argument einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="aacdd-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="aacdd-108">[out] Die Anzahl der Instanzen, die tatsächlich in Objekten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aacdd-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aacdd-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aacdd-109">Return Value</span></span>  
 <span data-ttu-id="aacdd-110">Die Methode gibt die folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="aacdd-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="aacdd-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aacdd-111">HRESULT</span></span>|<span data-ttu-id="aacdd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aacdd-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="aacdd-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aacdd-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="aacdd-114">Die tatsächliche Anzahl der Instanzen abgerufen, wie dargestellt in `pceltFetched`, ist kleiner als die Anzahl der Instanzen angefordert.</span><span class="sxs-lookup"><span data-stu-id="aacdd-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aacdd-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aacdd-115">Remarks</span></span>  
 <span data-ttu-id="aacdd-116">Die [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) Methode ruft die maximal `celt` Objekte, die an der aktuellen Position des Enumerators ab.</span><span class="sxs-lookup"><span data-stu-id="aacdd-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="aacdd-117">Wenn die Methode zurückgibt, `pceltFetched` enthält die tatsächliche Anzahl von Objekten abgerufen.</span><span class="sxs-lookup"><span data-stu-id="aacdd-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aacdd-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aacdd-118">Requirements</span></span>  
 <span data-ttu-id="aacdd-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aacdd-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aacdd-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aacdd-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aacdd-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aacdd-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aacdd-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aacdd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aacdd-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aacdd-123">See also</span></span>

- [<span data-ttu-id="aacdd-124">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aacdd-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="aacdd-125">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aacdd-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
