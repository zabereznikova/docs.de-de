---
title: ICorDebugProcess5::GetTypeID-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 499e1fd859a66bb6992c6d02a46e38c514503bd8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205590"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="2d102-102">ICorDebugProcess5::GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="2d102-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="2d102-103">Konvertiert eine Objekt Adresse in einen [COR_TYPEID](cor-typeid-structure.md) Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="2d102-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d102-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d102-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d102-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d102-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="2d102-106">in Die Objekt Adresse.</span><span class="sxs-lookup"><span data-stu-id="2d102-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="2d102-107">Ein Zeiger auf den [COR_TYPEID](cor-typeid-structure.md) Wert, durch den das-Objekt identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2d102-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d102-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d102-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d102-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d102-109">Requirements</span></span>  
 <span data-ttu-id="2d102-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d102-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d102-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d102-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d102-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d102-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d102-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d102-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d102-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d102-114">See also</span></span>

- [<span data-ttu-id="2d102-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d102-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="2d102-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2d102-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
