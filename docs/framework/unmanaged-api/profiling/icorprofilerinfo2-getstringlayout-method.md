---
title: ICorProfilerInfo2::GetStringLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: 257cf24fa476c75d6ec949e17a5b83fc015b8d43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496788"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a><span data-ttu-id="20ca7-102">ICorProfilerInfo2::GetStringLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="20ca7-102">ICorProfilerInfo2::GetStringLayout Method</span></span>
<span data-ttu-id="20ca7-103">Ruft Informationen zum Layout eines Zeichenfolgenobjekts ab.</span><span class="sxs-lookup"><span data-stu-id="20ca7-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="20ca7-104">Diese Methode ist in der .NET Framework 4 veraltet und wird durch die [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) -Methode abgelöst.</span><span class="sxs-lookup"><span data-stu-id="20ca7-104">This method is deprecated in the .NET Framework 4, and is superseded by the [ICorProfilerInfo3::GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ca7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="20ca7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ca7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="20ca7-106">Parameters</span></span>  
 `pBufferLengthOffset`  
 <span data-ttu-id="20ca7-107">vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge speichert.</span><span class="sxs-lookup"><span data-stu-id="20ca7-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string.</span></span> <span data-ttu-id="20ca7-108">Die Länge wird als gespeichert `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="20ca7-108">The length is stored as a `DWORD`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20ca7-109">Dieser Parameter gibt die Länge der Zeichenfolge selbst zurück, nicht die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="20ca7-109">This parameter returns the length of the string itself, not the length of the buffer.</span></span> <span data-ttu-id="20ca7-110">Die Länge des Puffers ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20ca7-110">The length of the buffer is no longer available.</span></span>  
  
 `PStringLengthOffset`  
 <span data-ttu-id="20ca7-111">vorgenommen Ein Zeiger auf den Offset der Position relativ zum `ObjectID` Zeiger, der die Länge der Zeichenfolge selbst speichert.</span><span class="sxs-lookup"><span data-stu-id="20ca7-111">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="20ca7-112">Die Länge wird als gespeichert `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="20ca7-112">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="20ca7-113">vorgenommen Ein Zeiger auf den Offset des Puffers relativ zum `ObjectID` Zeiger, der die Zeichenfolge von breit Zeichen speichert.</span><span class="sxs-lookup"><span data-stu-id="20ca7-113">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, that stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20ca7-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="20ca7-114">Remarks</span></span>  
 <span data-ttu-id="20ca7-115">Die- `GetStringLayout` Methode ruft die Offsets (relativ zum `ObjectID` Zeiger) der Speicherorte ab, an denen Folgendes gespeichert wird:</span><span class="sxs-lookup"><span data-stu-id="20ca7-115">The `GetStringLayout` method gets the offsets, relative to the `ObjectID` pointer, of the locations in which the following are stored:</span></span>  
  
- <span data-ttu-id="20ca7-116">Die Länge des Puffers der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="20ca7-116">The length of the string's buffer.</span></span>  
  
- <span data-ttu-id="20ca7-117">Die Länge der Zeichenfolge selbst.</span><span class="sxs-lookup"><span data-stu-id="20ca7-117">The length of the string itself.</span></span>  
  
- <span data-ttu-id="20ca7-118">Der Puffer, der die tatsächliche Zeichenfolge von breit Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="20ca7-118">The buffer that contains the actual string of wide characters.</span></span>  
  
 <span data-ttu-id="20ca7-119">Zeichen folgen können auf Null enden.</span><span class="sxs-lookup"><span data-stu-id="20ca7-119">Strings may be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ca7-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20ca7-120">Requirements</span></span>  
 <span data-ttu-id="20ca7-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20ca7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20ca7-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20ca7-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20ca7-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20ca7-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20ca7-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20ca7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ca7-125">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="20ca7-125">See also</span></span>

- [<span data-ttu-id="20ca7-126">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ca7-126">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="20ca7-127">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ca7-127">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
