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
ms.openlocfilehash: f2ea7ebff122622a0db46160d23574619664f8ad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745021"
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="90ff2-102">ICorDebugReferenceValue::Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="90ff2-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="90ff2-103">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="90ff2-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ff2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90ff2-104">Syntax</span></span>  
  
```cpp  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90ff2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90ff2-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="90ff2-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue ab, der das Objekt darstellt, zu dem dieses Objekt ICorDebugReferenceValue verweist.</span><span class="sxs-lookup"><span data-stu-id="90ff2-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90ff2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90ff2-107">Remarks</span></span>  
 <span data-ttu-id="90ff2-108">Die `ICorDebugValue` Objekt gilt nur, während dessen Verweis noch nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="90ff2-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ff2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90ff2-109">Requirements</span></span>  
 <span data-ttu-id="90ff2-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90ff2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90ff2-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90ff2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90ff2-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90ff2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90ff2-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90ff2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
