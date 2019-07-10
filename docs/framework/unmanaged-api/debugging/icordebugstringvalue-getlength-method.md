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
ms.openlocfilehash: b13fe65f892a222abb126aa9237b802507738b7f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771611"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="15400-102">ICorDebugStringValue::GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="15400-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="15400-103">Ruft die Anzahl der Zeichen in der Zeichenfolge durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="15400-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15400-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15400-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15400-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15400-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="15400-106">[out] Ein Zeiger auf einen Wert, der angibt, die Länge der Zeichenfolge, auf die von diesem `ICorDebugStringValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="15400-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15400-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15400-107">Requirements</span></span>  
 <span data-ttu-id="15400-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15400-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15400-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15400-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15400-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15400-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15400-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15400-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
