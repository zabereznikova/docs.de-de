---
title: ICorDebugReferenceValue::Dereference-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.Dereference
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type:
- apiref
ms.openlocfilehash: 6bb2a6b68a3c6e981a2d6c833d3f44d4c836bd23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124002"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="33053-102">ICorDebugReferenceValue::Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="33053-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="33053-103">Ruft das Objekt ab, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="33053-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33053-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33053-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33053-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33053-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="33053-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das das Objekt darstellt, auf das dieses ICorDebugReferenceValue-Objekt verweist.</span><span class="sxs-lookup"><span data-stu-id="33053-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33053-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33053-107">Remarks</span></span>  
 <span data-ttu-id="33053-108">Das `ICorDebugValue`-Objekt ist nur gültig, solange der zugehörige Verweis noch nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="33053-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33053-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33053-109">Requirements</span></span>  
 <span data-ttu-id="33053-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33053-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33053-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33053-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33053-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33053-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33053-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33053-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
