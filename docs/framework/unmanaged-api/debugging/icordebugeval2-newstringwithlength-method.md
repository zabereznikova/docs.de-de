---
title: ICorDebugEval2::NewStringWithLength-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b84a2fad53feda2996515781035c0eaad5828d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666985"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="c81ce-102">ICorDebugEval2::NewStringWithLength-Methode</span><span class="sxs-lookup"><span data-stu-id="c81ce-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="c81ce-103">Erstellt eine Zeichenfolge der angegebenen Länge und mit dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="c81ce-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c81ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c81ce-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c81ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c81ce-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="c81ce-106">[in] Ein Zeiger auf den Zeichenfolgenwert.</span><span class="sxs-lookup"><span data-stu-id="c81ce-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="c81ce-107">[in] Die Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c81ce-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c81ce-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c81ce-108">Remarks</span></span>  
 <span data-ttu-id="c81ce-109">Wenn die Zeichenfolge nachfolgende des Null-Zeichen wird erwartet in der verwalteten Zeichenfolge, der Aufrufer die `NewStringWithLength` Methode muss sicherstellen, dass die Länge der Zeichenfolge das abschließende Null-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="c81ce-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="c81ce-110">Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c81ce-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c81ce-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c81ce-111">Requirements</span></span>  
 <span data-ttu-id="c81ce-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c81ce-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c81ce-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c81ce-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c81ce-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c81ce-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c81ce-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c81ce-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
