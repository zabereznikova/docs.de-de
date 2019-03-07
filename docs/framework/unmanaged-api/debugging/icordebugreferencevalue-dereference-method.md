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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b436fa14322d444a6c8b515ba8e50698eecb95ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487017"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="5b081-102">ICorDebugReferenceValue::Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="5b081-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="5b081-103">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5b081-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b081-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b081-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b081-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b081-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="5b081-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue ab, der das Objekt darstellt, zu dem dieses Objekt ICorDebugReferenceValue verweist.</span><span class="sxs-lookup"><span data-stu-id="5b081-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b081-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b081-107">Remarks</span></span>  
 <span data-ttu-id="5b081-108">Die `ICorDebugValue` Objekt gilt nur, während dessen Verweis noch nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="5b081-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b081-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b081-109">Requirements</span></span>  
 <span data-ttu-id="5b081-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b081-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b081-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b081-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b081-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b081-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b081-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b081-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
