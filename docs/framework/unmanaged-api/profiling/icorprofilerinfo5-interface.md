---
title: ICorProfilerInfo5-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495626"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="ff02c-102">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff02c-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="ff02c-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="ff02c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ff02c-104">Eine Unterklasse von [ICorProfilerInfo4](icorprofilerinfo4-interface.md) , die Methoden bereitstellt, mit denen Codeprofiler mit der Common Language Runtime (CLR) kommunizieren können, um die Ereignisüberwachung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="ff02c-104">A subclass of [ICorProfilerInfo4](icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff02c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff02c-105">Methods</span></span>  
  
|<span data-ttu-id="ff02c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ff02c-106">Method</span></span>|<span data-ttu-id="ff02c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ff02c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff02c-108">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="ff02c-108">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="ff02c-109">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der CLR empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="ff02c-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="ff02c-110">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="ff02c-110">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="ff02c-111">Legt einen Wert fest, der die Ereignisarten spezifiziert, für die der Profiler Ereignisbenachrichtigungen von der CLR empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="ff02c-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff02c-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ff02c-112">Remarks</span></span>  
 <span data-ttu-id="ff02c-113">Die in dieser Schnittstelle verfügbaren Methoden sind zum Ersetzen der [ICorProfilerInfo:: GetEventMask](icorprofilerinfo-geteventmask-method.md) -Methode und der [ICorProfilerInfo::](icorprofilerinfo-seteventmask-method.md) -Methode bestimmt.</span><span class="sxs-lookup"><span data-stu-id="ff02c-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff02c-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff02c-114">Requirements</span></span>  
 <span data-ttu-id="ff02c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff02c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff02c-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff02c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff02c-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff02c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff02c-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ff02c-118">See also</span></span>

- [<span data-ttu-id="ff02c-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff02c-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
