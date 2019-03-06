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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471224"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="4d2ef-102">ICorDebugGenericValue::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="4d2ef-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="4d2ef-103">Kopiert den Wert dieses generischen in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d2ef-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d2ef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d2ef-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="4d2ef-106">[out] Ein Zeiger auf den Wert, der von diesem ICorDebugGenericValue-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="4d2ef-107">Der Wert kann es sich um einen einfachen Typ oder einen Verweistyp handelt (d. h. einen Zeiger) sein.</span><span class="sxs-lookup"><span data-stu-id="4d2ef-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2ef-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d2ef-108">Requirements</span></span>  
 <span data-ttu-id="4d2ef-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d2ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d2ef-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d2ef-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d2ef-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d2ef-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d2ef-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2ef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
