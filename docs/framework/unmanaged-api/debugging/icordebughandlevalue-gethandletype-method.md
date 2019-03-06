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
ms.openlocfilehash: ecc0b46618cd00ba4442e30c23a7b7e950382fee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475592"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="d0398-102">ICorDebugHandleValue::GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="d0398-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="d0398-103">Ruft einen Wert, der den Typ des Handles, die von diesem ICorDebugHandleValue-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d0398-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0398-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0398-104">Syntax</span></span>  
  
```  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0398-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0398-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="d0398-106">[out] Ein Zeiger auf einen Wert von CorDebugHandleType-Enumeration, die den Typ von diesem Handle angibt.</span><span class="sxs-lookup"><span data-stu-id="d0398-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0398-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0398-107">Requirements</span></span>  
 <span data-ttu-id="d0398-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0398-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0398-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0398-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0398-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0398-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0398-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0398-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
