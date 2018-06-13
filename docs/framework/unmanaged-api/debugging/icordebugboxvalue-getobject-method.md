---
title: ICorDebugBoxValue::GetObject-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfc8800915009912716ec2ed9044a633a8ad0582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401744"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="b3235-102">ICorDebugBoxValue::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="b3235-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="b3235-103">Ruft den durch Boxing konvertierten Wert.</span><span class="sxs-lookup"><span data-stu-id="b3235-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3235-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3235-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3235-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3235-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="b3235-106">[out] Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts, das durch Boxing konvertierten Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="b3235-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3235-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3235-107">Requirements</span></span>  
 <span data-ttu-id="b3235-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3235-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3235-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3235-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3235-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3235-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3235-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3235-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
