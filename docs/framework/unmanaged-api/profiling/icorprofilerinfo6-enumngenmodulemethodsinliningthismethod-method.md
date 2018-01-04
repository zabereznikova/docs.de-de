---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e11dd1c24001c764c82ed3f11336873ee57b2e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
[Wird nur in .NET Framework 4.6 und höheren Versionen unterstützt]  
  
 Gibt einen Enumerator für alle Methoden, die in einem bestimmten NGen-Modul und Inline eine bestimmte Methode definiert sind.  
  
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
 [out] Ein Flag, das angibt, ob `ppEnum` enthält alle Methoden-inlining eine bestimmte Methode.  Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `ppEnum`  
 [out] Ein Zeiger auf die Adresse eines Enumerators  
  
## <a name="remarks"></a>Hinweise  
 `inlineeModuleId`und `inlineeMethodId` bilden zusammen den vollständigen Bezeichner für die Methode, die inline gesetzt werden kann. Nehmen wir beispielsweise an das Modul `A` definiert eine Methode `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 "und" Module Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 Ermöglicht darüber hinaus vorausgesetzt, die `Fancy.AddTwice` Inlines der Aufruf zum `SimpleAdd`. Ein Profiler können mit diesem Enumerator finden Sie im Modul B welche Inline definiert alle Methoden `Simple.Add`, und das Ergebnis würde aufzählen `AddTwice`.  `inlineeModuleId`Der Bezeichner des Moduls `A`, und `inlineeeMethodId` ist der Bezeichner des `Simple.Add(int a, int b)`.  
  
 Wenn `incompleteData` ist nach der Funktion "true" zurückgibt, der Enumerator enthält nicht alle Methoden-inlining eine bestimmte Methode. Dies kann auftreten, wenn ein oder direkte oder indirekte Abhängigkeiten Striktheit mit Bedacht vorgegangen Modul noch noch nicht geladen wurde. Wenn ein Profiler die genaue Daten benötigt, sollte er einem späteren Zeitpunkt erneut, wenn mehrere Module, vorzugsweise auf jede Laden von Modulen geladen sind.  
  
 Die `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen umgehen für ReJIT inlining. ReJIT ermöglicht einen Profiler, ändern Sie die Implementierung einer Methode, und klicken Sie dann für sie neuen Code erstellen, bei laufendem Betrieb. Wir könnten z. B. ändern `Simple.Add` wie folgt:  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 Aber da `Fancy.AddTwice` wurde bereits inline `Simple.Add`, weiterhin das gleiche Verhalten wie zuvor aufweisen. Um diese Einschränkung zu umgehen, der Aufrufer muss für alle Methoden in allen Modulen, Inline suchen `Simple.Add` und `ICorProfilerInfo5::RequestRejit` auf jede dieser Methoden. Wenn die Methoden erneut kompilierte sind, müssen sie das neue Verhalten der `Simple.Add` anstelle des alten Verhaltens.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo6-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
