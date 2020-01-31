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
ms.openlocfilehash: 9153503fc114b0e4052265fca7c9399510d687ef
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792318"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="8ac11-102">ICorDebugProcess5::GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="8ac11-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="8ac11-103">Konvertiert eine Objekt Adresse in einen [COR_TYPEID](cor-typeid-structure.md) Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="8ac11-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ac11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ac11-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ac11-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8ac11-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="8ac11-106">in Die Objekt Adresse.</span><span class="sxs-lookup"><span data-stu-id="8ac11-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="8ac11-107">Ein Zeiger auf den [COR_TYPEID](cor-typeid-structure.md) Wert, durch den das-Objekt identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8ac11-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ac11-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ac11-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ac11-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ac11-109">Requirements</span></span>  
 <span data-ttu-id="8ac11-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ac11-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ac11-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ac11-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ac11-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ac11-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ac11-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ac11-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ac11-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ac11-114">See also</span></span>

- [<span data-ttu-id="8ac11-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ac11-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="8ac11-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ac11-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
