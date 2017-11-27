---
title: ICorDebugStringValue::GetLength-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c072e7420e400e6402c8697eefc62c658c590261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="bc401-102">ICorDebugStringValue::GetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="bc401-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="bc401-103">Ruft die Anzahl der Zeichen in der Zeichenfolge durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bc401-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc401-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc401-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc401-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc401-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="bc401-106">[out] Ein Zeiger auf einen Wert, der angibt, die Länge der Zeichenfolge, auf die von diesem `ICorDebugStringValue` Objekt.</span><span class="sxs-lookup"><span data-stu-id="bc401-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc401-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc401-107">Requirements</span></span>  
 <span data-ttu-id="bc401-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc401-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc401-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc401-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc401-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc401-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc401-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc401-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
