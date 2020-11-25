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
ms.openlocfilehash: df151e9fc89214d0851ebe60c7ebdb87224f880c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719072"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="c7ec7-102">ICorDebugBoxValue::GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="c7ec7-102">ICorDebugBoxValue::GetObject Method</span></span>

<span data-ttu-id="c7ec7-103">Ruft den geboxten Wert ab.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ec7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7ec7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ec7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7ec7-105">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="c7ec7-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugObjectValue-Objekts, das den geboxten Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7ec7-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ec7-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7ec7-107">Requirements</span></span>  

 <span data-ttu-id="c7ec7-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7ec7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ec7-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7ec7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7ec7-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ec7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ec7-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ec7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
