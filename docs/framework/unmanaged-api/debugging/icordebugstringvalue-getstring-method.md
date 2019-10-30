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
ms.openlocfilehash: c4b01b2c346d3173b2a5ecc144474d7fb1e6dce5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138970"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="108af-102">ICorDebugStringValue::GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="108af-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="108af-103">Ruft die Zeichenfolge ab, auf die von diesem icorentbugstringvalue verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="108af-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="108af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="108af-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="108af-106">[in] Die Größe des `szString`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="108af-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="108af-107">vorgenommen Ein Zeiger auf die Anzahl der Zeichen, die im `szString` Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="108af-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="108af-108">vorgenommen Ein Array, das die abgerufene Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="108af-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108af-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="108af-109">Requirements</span></span>  
 <span data-ttu-id="108af-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108af-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="108af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="108af-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108af-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
