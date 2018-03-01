---
title: ICorDebugBoxValue::GetObject-Methode
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
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e71da40af57d00e4651c094ddad9c86fc6fe636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="9ad4d-102">ICorDebugBoxValue::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="9ad4d-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="9ad4d-103">Ruft den durch Boxing konvertierten Wert.</span><span class="sxs-lookup"><span data-stu-id="9ad4d-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ad4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ad4d-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ad4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ad4d-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9ad4d-106">[out] Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts, das durch Boxing konvertierten Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ad4d-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ad4d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ad4d-107">Requirements</span></span>  
 <span data-ttu-id="9ad4d-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ad4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ad4d-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ad4d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ad4d-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ad4d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ad4d-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ad4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
