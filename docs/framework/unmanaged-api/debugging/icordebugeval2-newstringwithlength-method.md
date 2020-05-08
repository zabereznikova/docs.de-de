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
ms.openlocfilehash: a2b76cb59a95082e0cf9c0884b8277cca3c8fe8d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976069"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="7548e-102">ICorDebugEval2::NewStringWithLength-Methode</span><span class="sxs-lookup"><span data-stu-id="7548e-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="7548e-103">Erstellt eine Zeichenfolge mit der angegebenen Länge und dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="7548e-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7548e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7548e-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7548e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7548e-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="7548e-106">in Ein Zeiger auf den Zeichen folgen Wert.</span><span class="sxs-lookup"><span data-stu-id="7548e-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="7548e-107">in Länge der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7548e-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7548e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7548e-108">Remarks</span></span>  
 <span data-ttu-id="7548e-109">Wenn erwartet wird, dass das nachfolgende NULL-Zeichen in der verwalteten Zeichenfolge enthalten ist, muss `NewStringWithLength` der Aufrufer der-Methode sicherstellen, dass die Zeichen folgen Länge das nachfolgende NULL-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="7548e-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="7548e-110">Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7548e-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7548e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7548e-111">Requirements</span></span>  
 <span data-ttu-id="7548e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7548e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7548e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7548e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7548e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7548e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7548e-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7548e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
