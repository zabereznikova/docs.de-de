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
ms.openlocfilehash: dc4df7e7cb93f137013d0a0e4d805c7563d4fe1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697895"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="f87fc-102">ICorProfilerInfo3::GetStringLayout2-Methode</span><span class="sxs-lookup"><span data-stu-id="f87fc-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>

<span data-ttu-id="f87fc-103">Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.</span><span class="sxs-lookup"><span data-stu-id="f87fc-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="f87fc-104">Diese Methode ersetzt die [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f87fc-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87fc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f87fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f87fc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f87fc-106">Parameters</span></span>  

 `pStringLengthOffset`  
 <span data-ttu-id="f87fc-107">vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert.</span><span class="sxs-lookup"><span data-stu-id="f87fc-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="f87fc-108">Die Länge wird als gespeichert `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="f87fc-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f87fc-109">vorgenommen Ein Zeiger auf den Offset des Puffers relativ zum `ObjectID` Zeiger, der die Zeichenfolge von breit Zeichen speichert.</span><span class="sxs-lookup"><span data-stu-id="f87fc-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f87fc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f87fc-110">Remarks</span></span>  

 <span data-ttu-id="f87fc-111">Zeichen folgen können NULL-terminierte Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="f87fc-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f87fc-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f87fc-112">Requirements</span></span>  

 <span data-ttu-id="f87fc-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87fc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87fc-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f87fc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f87fc-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f87fc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f87fc-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87fc-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f87fc-117">See also</span></span>

- [<span data-ttu-id="f87fc-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f87fc-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f87fc-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f87fc-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
