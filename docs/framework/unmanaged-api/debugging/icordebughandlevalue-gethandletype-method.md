---
title: ICorDebugHandleValue::GetHandleType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51fd8e9728955e8f426a38b8bf6cdc78dfa9bbde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412346"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="1bdd3-102">ICorDebugHandleValue::GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="1bdd3-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="1bdd3-103">Ruft einen Wert, der die Art des Handles, die von diesem Objekt ICorDebugHandleValue verwiesen angibt.</span><span class="sxs-lookup"><span data-stu-id="1bdd3-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdd3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bdd3-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bdd3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1bdd3-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="1bdd3-106">[out] Ein Zeiger auf einen Wert von CorDebugHandleType-Enumeration, die den Typ dieser Anforderung angibt.</span><span class="sxs-lookup"><span data-stu-id="1bdd3-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bdd3-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1bdd3-107">Requirements</span></span>  
 <span data-ttu-id="1bdd3-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bdd3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bdd3-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bdd3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bdd3-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bdd3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bdd3-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bdd3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
