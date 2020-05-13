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
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377153"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="0cda8-102">ICorDebugThread2::GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="0cda8-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="0cda8-103">Ruft Informationen über die aktive Funktion in den einzelnen Rahmen dieses Threads ab.</span><span class="sxs-lookup"><span data-stu-id="0cda8-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cda8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cda8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cda8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cda8-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="0cda8-106">[in] Die Größe des `pFunctions`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0cda8-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="0cda8-107">vorgenommen Ein Zeiger auf die Anzahl der-Objekte, die im-Array zurückgegeben werden `pFunctions` .</span><span class="sxs-lookup"><span data-stu-id="0cda8-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="0cda8-108">Die Anzahl der zurückgegebenen Objekte ist gleich der Anzahl der verwalteten Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="0cda8-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="0cda8-109">[in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen in den Frames dieses Threads enthält.</span><span class="sxs-lookup"><span data-stu-id="0cda8-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="0cda8-110">Das erste-Element wird für den blattrahmen verwendet usw. zurück zum Stamm des Stapels.</span><span class="sxs-lookup"><span data-stu-id="0cda8-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cda8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cda8-111">Remarks</span></span>  
 <span data-ttu-id="0cda8-112">Wenn `pFunctions` bei Eingabe NULL ist, `GetActiveFunctions` gibt nur die Anzahl der Funktionen zurück, die sich auf dem Stapel befinden.</span><span class="sxs-lookup"><span data-stu-id="0cda8-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="0cda8-113">Das heißt, wenn `pFunctions` bei Eingabe NULL ist, `GetActiveFunctions` gibt nur in einen Wert zurück `pcFunctions` .</span><span class="sxs-lookup"><span data-stu-id="0cda8-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="0cda8-114">Die `GetActiveFunctions` -Methode ist als Optimierung gedacht, um die gleichen Informationen aus Frames in einer Stapel Überwachung zu erhalten, und schließt nur Frames ein, die ein ICorDebugILFrame-Objekt für Sie in der vollständigen Stapel Überwachung hätten.</span><span class="sxs-lookup"><span data-stu-id="0cda8-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cda8-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0cda8-115">Requirements</span></span>  
 <span data-ttu-id="0cda8-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cda8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cda8-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cda8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cda8-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cda8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cda8-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cda8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
