---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568152"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
[Wird nur in der .NET Framework 4.6 und höheren Versionen unterstützt]  
  
 Gibt einen Enumerator für alle Methoden, die in einem bestimmten NGen-Modul und Inline einer bestimmten Methode definiert sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `inlinersModuleId`  
 [in] Der Bezeichner des NGen-Modul.  
  
 `inlineeModuleId`  
 [in] Der Bezeichner eines Moduls, das definiert `inlineeMethodId`. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `inlineeMethodId`  
 [in] Der Bezeichner einer Inline-Methode. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `incompleteData`  
 [out] Ein Flag, das angibt, ob `ppEnum` enthält alle Methoden, die inlineersetzung eine bestimmte Methode.  Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `ppEnum`  
 [out] Ein Zeiger auf die Adresse eines Enumerators  
  
## <a name="remarks"></a>Hinweise  
 `inlineeModuleId` und `inlineeMethodId` zusammen bilden den vollständigen Bezeichner für die Methode, die intern sein können. Nehmen wir beispielsweise an das Modul `A` definiert eine Methode `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 und das Modul Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Ermöglicht darüber hinaus vorausgesetzt, die `Fancy.AddTwice` wird der Aufruf zum `SimpleAdd`. Ein Profiler kann dieser Enumerator verwenden, finden Sie in Modul B die Inline definiert alle Methoden `Simple.Add`, und das Ergebnis würde auflisten `AddTwice`.  `inlineeModuleId` Der Bezeichner des Moduls `A`, und `inlineeeMethodId` ist der Bezeichner des `Simple.Add(int a, int b)`.  
  
 Wenn `incompleteData` ist nach der Funktion "true" zurückgibt, der Enumerator enthält nicht alle Methoden, die inlineersetzung eine bestimmte Methode. Dies kann auftreten, wenn ein oder direkte oder indirekte Abhängigkeiten des Inliners-Moduls wurde noch nicht getan haben geladen. Wenn ein Profiler die genaue Daten benötigt, sollte es später noch Mal, wenn weitere Module, vorzugsweise auf jedem Modul laden geladen werden.  
  
 Die `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen umgehen für ReJIT inlining. ReJIT kann es sich um einen Profiler, ändern Sie die Implementierung einer Methode, und klicken Sie dann für sie neuen Code erstellen, im laufenden Betrieb. Wir könnten z. B. ändern `Simple.Add` wie folgt:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Aber da `Fancy.AddTwice` hat bereits inline `Simple.Add`, es verfügt auch weiterhin über das gleiche Verhalten wie zuvor. Zur Umgehung dieser Einschränkung der Aufrufer muss für alle Methoden in allen Modulen, Inline suchen `Simple.Add` und `ICorProfilerInfo5::RequestRejit` auf jede dieser Methoden. Wenn die Methoden neu kompilierten sind, müssen sie das neue Verhalten der `Simple.Add` anstatt das alte Verhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo6-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
