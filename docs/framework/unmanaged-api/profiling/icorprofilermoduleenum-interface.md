---
title: ICorProfilerModuleEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: 2713fa90240cb0bf41f455b6ed65d76c568a2cf8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868264"
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum-Schnittstelle
Stellt Methoden bereit, um eine Auflistung von Modulen, die von der Anwendung oder dem Profiler geladen wurden, sequenziell zu durchlaufen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[Clone-Methode](icorprofilermoduleenum-clone-method.md)|Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerModuleEnum`-Schnittstelle ab.|  
|[GetCount-Methode](icorprofilermoduleenum-getcount-method.md)|Ruft die Anzahl der verwalteten Module ab, die in die Anwendung geladen wurden.|  
|[Next-Methode](icorprofilermoduleenum-next-method.md)|Ruft die angegebene Anzahl zusammenhängender Module aus einer sequenziellen Auflistung von Objekten ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.|  
|[Reset-Methode](icorprofilermoduleenum-reset-method.md)|Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.|  
|[Skip-Methode](icorprofilermoduleenum-skip-method.md)|Verschiebt die Cursorposition des Enumerators so, dass die angegebene Anzahl von Elementen übersprungen wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorProfilerModuleEnum`-Schnittstelle ist ein Enumerator. Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen. Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [EnumModules-Methode](icorprofilerinfo3-enummodules-method.md)
