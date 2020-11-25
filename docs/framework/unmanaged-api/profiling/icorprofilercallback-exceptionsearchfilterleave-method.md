---
title: ICorProfilerCallback::ExceptionSearchFilterLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: e9679b75e773ec884905ea773e804e03607a61d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699845"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="89fbb-102">ICorProfilerCallback::ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="89fbb-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>

<span data-ttu-id="89fbb-103">Benachrichtigt den Profiler, dass die Ausführung eines Benutzer Filters soeben abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="89fbb-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89fbb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89fbb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="89fbb-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89fbb-105">Requirements</span></span>  

 <span data-ttu-id="89fbb-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89fbb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89fbb-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89fbb-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89fbb-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89fbb-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89fbb-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89fbb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fbb-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89fbb-110">See also</span></span>

- [<span data-ttu-id="89fbb-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89fbb-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="89fbb-112">ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="89fbb-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
