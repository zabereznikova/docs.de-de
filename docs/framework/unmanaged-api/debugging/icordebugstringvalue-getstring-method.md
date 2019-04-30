---
title: ICorDebugStringValue::GetString-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bf62d8855b3f9de5629b9cfc6e0bcd0878a0d17
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987362"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="708b7-102">ICorDebugStringValue::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="708b7-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="708b7-103">Ruft die Zeichenfolge, die durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="708b7-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="708b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="708b7-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="708b7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="708b7-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="708b7-106">[in] Die Größe des `szString`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="708b7-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="708b7-107">[out] Ein Zeiger auf die Anzahl der Zeichen zurückgegeben werden, der `szString` Array.</span><span class="sxs-lookup"><span data-stu-id="708b7-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="708b7-108">[out] Ein Array, das die abgerufene Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="708b7-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="708b7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="708b7-109">Requirements</span></span>  
 <span data-ttu-id="708b7-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="708b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708b7-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="708b7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="708b7-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="708b7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="708b7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
