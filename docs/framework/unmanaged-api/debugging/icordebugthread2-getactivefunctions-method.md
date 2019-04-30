---
title: ICorDebugThread2::GetActiveFunctions-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed13f78d5a1f6d54b12c86613715f4878a521bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993966"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="ec50e-102">ICorDebugThread2::GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="ec50e-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="ec50e-103">Ruft Informationen über die aktiven Funktion in dieses Threads Frames ab.</span><span class="sxs-lookup"><span data-stu-id="ec50e-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec50e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec50e-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec50e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec50e-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="ec50e-106">[in] Die Größe des `pFunctions`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="ec50e-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="ec50e-107">[out] Ein Zeiger auf die Anzahl der zurückgegebenen Objekte die `pFunctions` Array.</span><span class="sxs-lookup"><span data-stu-id="ec50e-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="ec50e-108">Die Anzahl der zurückgegebenen Objekte werden gleich der Anzahl der verwalteten Frames im Stapel.</span><span class="sxs-lookup"><span data-stu-id="ec50e-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="ec50e-109">[in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen in dieses Threads Frames enthält.</span><span class="sxs-lookup"><span data-stu-id="ec50e-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="ec50e-110">Das erste Element wird für die Endframe und usw. bis zurück in das Stammverzeichnis des Stapels verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec50e-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec50e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec50e-111">Remarks</span></span>  
 <span data-ttu-id="ec50e-112">Wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt nur die Anzahl der Funktionen, die im Stapel befinden.</span><span class="sxs-lookup"><span data-stu-id="ec50e-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="ec50e-113">D. h. wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt einen Wert nur in `pcFunctions`.</span><span class="sxs-lookup"><span data-stu-id="ec50e-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="ec50e-114">Die `GetActiveFunctions` -Methode dient als eine Optimierung über die gleichen Informationen abrufen, aus der Bilder in eine stapelüberwachung und enthält nur die Frames, die ein ICorDebugILFrame-Objekt für diese in die vollständige stapelüberwachung, müssten.</span><span class="sxs-lookup"><span data-stu-id="ec50e-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec50e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec50e-115">Requirements</span></span>  
 <span data-ttu-id="ec50e-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec50e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec50e-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec50e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec50e-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec50e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec50e-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec50e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
