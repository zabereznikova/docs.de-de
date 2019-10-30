---
title: ICorDebugGenericValue::GetValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 7923008eecb9011bead685fbbb7f05f81f12329b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138576"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="d8c15-102">ICorDebugGenericValue::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d8c15-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="d8c15-103">Kopiert den Wert dieses generischen in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="d8c15-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8c15-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8c15-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8c15-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="d8c15-106">vorgenommen Ein Zeiger auf den Wert, der durch dieses ICorDebugGenericValue-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d8c15-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="d8c15-107">Der Wert kann ein einfacher Typ oder ein Verweistyp sein (d. h. ein Zeiger).</span><span class="sxs-lookup"><span data-stu-id="d8c15-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c15-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8c15-108">Requirements</span></span>  
 <span data-ttu-id="d8c15-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8c15-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c15-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8c15-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8c15-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8c15-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8c15-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c15-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
