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
ms.openlocfilehash: bc7d99d0ddb443cba227b7bad0cd53edb94c9101
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138542"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="a391e-102">ICorDebugHandleValue::GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="a391e-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="a391e-103">Ruft einen Wert ab, der die Art des Handles angibt, auf das von diesem ICorDebugHandleValue-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a391e-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a391e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a391e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a391e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a391e-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="a391e-106">vorgenommen Ein Zeiger auf einen Wert der CorDebugHandleType-Enumeration, der den Typ dieses Handles angibt.</span><span class="sxs-lookup"><span data-stu-id="a391e-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a391e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a391e-107">Requirements</span></span>  
 <span data-ttu-id="a391e-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a391e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a391e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a391e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a391e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a391e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a391e-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a391e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
