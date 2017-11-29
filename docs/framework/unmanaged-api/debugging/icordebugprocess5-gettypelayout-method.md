---
title: ICorDebugProcess5::GetTypeLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2f36b78558f8a8005735166436ad3dead28992e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="b530b-102">ICorDebugProcess5::GetTypeLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="b530b-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="b530b-103">Ruft Informationen zum Layout eines Objekts im Arbeitsspeicher auf Grundlage seines Bezeichners Typ ab.</span><span class="sxs-lookup"><span data-stu-id="b530b-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b530b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b530b-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b530b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b530b-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="b530b-106">[in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das den Typ angibt, deren Layout erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="b530b-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="b530b-107">[out] Ein Zeiger auf eine [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) -Struktur, die Informationen zum Layout des Objekts im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="b530b-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b530b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b530b-108">Remarks</span></span>  
 <span data-ttu-id="b530b-109">Die `ICorDebugProcess5::GetTypeLayout` Methode bietet Informationen zu einem Objekt basierend auf seiner [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), der zurückgegeben wird, indem Sie eine Zahl von sonstigen [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="b530b-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="b530b-110">Die Informationen werden bereitgestellt, indem eine [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) -Struktur, die von der-Methode aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b530b-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b530b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b530b-111">Requirements</span></span>  
 <span data-ttu-id="b530b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b530b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b530b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b530b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b530b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b530b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b530b-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b530b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b530b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b530b-116">See Also</span></span>  
 [<span data-ttu-id="b530b-117">COR_TYPE_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="b530b-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [<span data-ttu-id="b530b-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b530b-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="b530b-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b530b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
