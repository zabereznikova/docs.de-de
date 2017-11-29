---
title: ICorDebugStringValue::GetString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 077f8488419cee434a8dc8266b0814dfd4196b03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="84072-102">ICorDebugStringValue::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="84072-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="84072-103">Ruft die Zeichenfolge, die durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84072-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84072-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84072-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84072-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84072-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="84072-106">[in] Die Größe des `szString`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="84072-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="84072-107">[out] Ein Zeiger auf die Anzahl der Zeichen zurückgegeben, die der `szString` Array.</span><span class="sxs-lookup"><span data-stu-id="84072-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="84072-108">[out] Ein Array, das die abgerufene Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="84072-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84072-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84072-109">Requirements</span></span>  
 <span data-ttu-id="84072-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84072-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84072-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84072-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84072-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84072-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84072-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84072-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
