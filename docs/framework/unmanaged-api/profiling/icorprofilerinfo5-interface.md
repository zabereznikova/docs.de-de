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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e55d52b3ba3bb2b932627ca364ed8f6084fcf26
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536463"
---
# <a name="icorprofilerinfo5-interface"></a><span data-ttu-id="ca75f-102">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca75f-102">ICorProfilerInfo5 Interface</span></span>
<span data-ttu-id="ca75f-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="ca75f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ca75f-104">Eine Unterklasse von [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) , die Methoden für die Verwendung durch Codeprofiler für Kommunikation mit die common Language Runtime (CLR), um die Steuerung der ereignisüberwachung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ca75f-104">A subclass of [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) that provides methods for use by code profilers to communicate with the common language runtime (CLR) to control event monitoring.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca75f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca75f-105">Methods</span></span>  
  
|<span data-ttu-id="ca75f-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ca75f-106">Method</span></span>|<span data-ttu-id="ca75f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca75f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca75f-108">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="ca75f-108">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|<span data-ttu-id="ca75f-109">Ruft die aktuellen Ereigniskategorien ab, für die der Profiler Benachrichtigungen von der CLR empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="ca75f-109">Gets the current event categories for which the profiler wants to receive notifications from the CLR.</span></span>|  
|[<span data-ttu-id="ca75f-110">SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="ca75f-110">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|<span data-ttu-id="ca75f-111">Legt einen Wert fest, der die Ereignisarten spezifiziert, für die der Profiler Ereignisbenachrichtigungen von der CLR empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="ca75f-111">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca75f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca75f-112">Remarks</span></span>  
 <span data-ttu-id="ca75f-113">Auf dieser Schnittstelle verfügbaren Methoden ersetzen sollen die [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) und [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methoden.</span><span class="sxs-lookup"><span data-stu-id="ca75f-113">The methods available on this interface are intended to replace the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca75f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca75f-114">Requirements</span></span>  
 <span data-ttu-id="ca75f-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca75f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca75f-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca75f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca75f-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca75f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca75f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca75f-118">See also</span></span>
- [<span data-ttu-id="ca75f-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca75f-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
