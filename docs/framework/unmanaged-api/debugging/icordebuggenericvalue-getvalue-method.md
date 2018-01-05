---
title: ICorDebugGenericValue::GetValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue.GetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ebb681d32c3ba805fd2e413ceeb007cb2cee57f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="d4a84-102">ICorDebugGenericValue::GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d4a84-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="d4a84-103">Kopiert den Wert dieses generischen in den angegebenen Puffer.</span><span class="sxs-lookup"><span data-stu-id="d4a84-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4a84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4a84-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4a84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4a84-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="d4a84-106">[out] Ein Zeiger auf den Wert, der von diesem ICorDebugGenericValue-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d4a84-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="d4a84-107">Der Wert kann ein einfacher Typ oder ein Verweistyp (d. h. ein Zeiger) sein.</span><span class="sxs-lookup"><span data-stu-id="d4a84-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4a84-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4a84-108">Requirements</span></span>  
 <span data-ttu-id="d4a84-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4a84-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4a84-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4a84-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4a84-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4a84-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4a84-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4a84-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
