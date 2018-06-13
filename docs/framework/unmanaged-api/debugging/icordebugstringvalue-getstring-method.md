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
ms.openlocfilehash: 63d3df561a3b48a4b26426235455ef1a074512f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417961"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="23090-102">ICorDebugStringValue::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="23090-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="23090-103">Ruft die Zeichenfolge, die durch ICorDebugStringValue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="23090-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23090-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23090-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23090-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23090-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="23090-106">[in] Die Größe des `szString`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="23090-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="23090-107">[out] Ein Zeiger auf die Anzahl der Zeichen zurückgegeben, die der `szString` Array.</span><span class="sxs-lookup"><span data-stu-id="23090-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="23090-108">[out] Ein Array, das die abgerufene Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="23090-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23090-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23090-109">Requirements</span></span>  
 <span data-ttu-id="23090-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23090-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23090-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23090-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23090-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23090-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23090-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23090-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
