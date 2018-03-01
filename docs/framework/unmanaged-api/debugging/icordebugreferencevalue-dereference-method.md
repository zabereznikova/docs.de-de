---
title: ICorDebugReferenceValue::Dereference-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0dbf2775217a78c1cbb9a96093354f0fc0b278bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="72d35-102">ICorDebugReferenceValue::Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="72d35-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="72d35-103">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="72d35-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72d35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72d35-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72d35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72d35-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="72d35-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue ab, der das Objekt darstellt, zu dem dieses Objekt ICorDebugReferenceValue verweist.</span><span class="sxs-lookup"><span data-stu-id="72d35-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72d35-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72d35-107">Remarks</span></span>  
 <span data-ttu-id="72d35-108">Die `ICorDebugValue` Objekt gilt nur, während dessen Verweis noch nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="72d35-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72d35-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72d35-109">Requirements</span></span>  
 <span data-ttu-id="72d35-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72d35-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72d35-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72d35-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72d35-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72d35-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72d35-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72d35-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
