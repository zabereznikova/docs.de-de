---
title: ICorProfilerInfo3::GetStringLayout2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ac724db000f84e37995a34e808d3df4b1e7a960
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765407"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="b14cb-102">ICorProfilerInfo3::GetStringLayout2-Methode</span><span class="sxs-lookup"><span data-stu-id="b14cb-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="b14cb-103">Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.</span><span class="sxs-lookup"><span data-stu-id="b14cb-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="b14cb-104">Diese Methode ersetzt die [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b14cb-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b14cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b14cb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b14cb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b14cb-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="b14cb-107">[out] Ein Zeiger auf den Offset der Position, relativ zu den `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert.</span><span class="sxs-lookup"><span data-stu-id="b14cb-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="b14cb-108">Die Dauer, gespeichert als eine `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="b14cb-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="b14cb-109">[out] Ein Zeiger auf den Offset des Puffers, relativ zu den `ObjectID` Zeiger, der die Zeichenfolge mit Breitzeichen speichert.</span><span class="sxs-lookup"><span data-stu-id="b14cb-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b14cb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b14cb-110">Remarks</span></span>  
 <span data-ttu-id="b14cb-111">Zeichenfolgen können, oder es können keine Null-terminiert sein.</span><span class="sxs-lookup"><span data-stu-id="b14cb-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b14cb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b14cb-112">Requirements</span></span>  
 <span data-ttu-id="b14cb-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b14cb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b14cb-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b14cb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b14cb-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b14cb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b14cb-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b14cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b14cb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b14cb-117">See also</span></span>

- [<span data-ttu-id="b14cb-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b14cb-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b14cb-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b14cb-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
