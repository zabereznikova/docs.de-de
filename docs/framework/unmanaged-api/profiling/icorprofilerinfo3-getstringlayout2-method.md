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
ms.openlocfilehash: 1e3dc4735af68da7f76fc6fce84d2dd4ac3f576e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449655"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="8ea44-102">ICorProfilerInfo3::GetStringLayout2-Methode</span><span class="sxs-lookup"><span data-stu-id="8ea44-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="8ea44-103">Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.</span><span class="sxs-lookup"><span data-stu-id="8ea44-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="8ea44-104">Diese Methode ersetzt die [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8ea44-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ea44-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ea44-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ea44-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ea44-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="8ea44-107">vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="8ea44-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="8ea44-108">Die Länge wird als `DWORD`gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8ea44-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="8ea44-109">vorgenommen Ein Zeiger auf den Offset des Puffers relativ zum `ObjectID` Zeiger, der die Zeichenfolge von breit Zeichen speichert.</span><span class="sxs-lookup"><span data-stu-id="8ea44-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ea44-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ea44-110">Remarks</span></span>  
 <span data-ttu-id="8ea44-111">Zeichen folgen können NULL-terminierte Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="8ea44-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ea44-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8ea44-112">Requirements</span></span>  
 <span data-ttu-id="8ea44-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ea44-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ea44-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ea44-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ea44-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ea44-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ea44-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ea44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea44-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea44-117">See also</span></span>

- [<span data-ttu-id="8ea44-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ea44-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="8ea44-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8ea44-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
