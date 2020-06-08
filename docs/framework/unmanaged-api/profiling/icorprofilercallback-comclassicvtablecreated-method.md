---
title: ICorProfilerCallback::COMClassicVTableCreated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
ms.openlocfilehash: 6c9ec6af90cc47c3c01621563a9813789c25aa1d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500337"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a>ICorProfilerCallback::COMClassicVTableCreated-Methode
Benachrichtigt den Profiler, dass eine COM-Interop-Vtable für die angegebene IID und Klasse erstellt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a>Parameter

- `wrappedClasId`

  \[in] die ID der Klasse, für die die Vtable erstellt wurde.

- `implementedIID`

  \[in] die ID der Schnittstelle, die von der-Klasse implementiert wird. Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern ist.

- `pVTable`

  \[in] ein Zeiger auf den Anfang der vtable.

- `cSlots`

  \[in] die Anzahl der Slots in der vtable.

## <a name="remarks"></a>Bemerkungen  
 Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden. Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.  
  
 Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
- [COMClassicVTableDestroyed-Methode](icorprofilercallback-comclassicvtabledestroyed-method.md)
