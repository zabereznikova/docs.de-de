---
title: ICorDebugGenericValue::SetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.SetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae64fcccb49123f34cca2622a972a89bf700904f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476684"
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="20c54-102">ICorDebugGenericValue::SetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="20c54-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="20c54-103">Kopiert einen neuen Wert aus dem angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="20c54-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20c54-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20c54-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20c54-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="20c54-106">[in] Ein Zeiger auf den Puffer, aus dem den Wert kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20c54-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20c54-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20c54-107">Remarks</span></span>  
 <span data-ttu-id="20c54-108">Für Verweistypen ist der Wert für den Verweis, nicht den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="20c54-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c54-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20c54-109">Requirements</span></span>  
 <span data-ttu-id="20c54-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20c54-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c54-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20c54-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20c54-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c54-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20c54-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
