---
title: ICorDebugStringValue::GetLength-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b168673e76beddd8ae0479b8daae009c5f057b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494661"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="afdea-102">ICorDebugStringValue::GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="afdea-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="afdea-103">Ruft die Anzahl der Zeichen in der Zeichenfolge durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="afdea-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afdea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afdea-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afdea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afdea-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="afdea-106">[out] Ein Zeiger auf einen Wert, der angibt, die Länge der Zeichenfolge, auf die von diesem `ICorDebugStringValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="afdea-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afdea-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="afdea-107">Requirements</span></span>  
 <span data-ttu-id="afdea-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afdea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afdea-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afdea-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afdea-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afdea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afdea-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afdea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
