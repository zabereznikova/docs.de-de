---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67ae413ae8944757fc90bcde752b9a5fe53cc68f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948524"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode

Gibt einen Enumerator für alle Methoden, die in einem bestimmten NGen-Modul und Inline einer bestimmten Methode definiert sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>Parameter

`inlinersModuleId`\
[in] Der Bezeichner des NGen-Modul.

`inlineeModuleId`\
[in] Der Bezeichner eines Moduls, das definiert `inlineeMethodId`. Weitere Informationen finden Sie im Abschnitt Hinweise.

`inlineeMethodId`\
[in] Der Bezeichner einer Inline-Methode. Weitere Informationen finden Sie im Abschnitt Hinweise.

`incompleteData`\
[out] Ein Flag, das angibt, ob `ppEnum` enthält alle Methoden, die inlineersetzung eine bestimmte Methode.  Weitere Informationen finden Sie im Abschnitt Hinweise.

`ppEnum`\
[out] Ein Zeiger auf die Adresse eines Enumerators

## <a name="remarks"></a>Hinweise

`inlineeModuleId` und `inlineeMethodId` zusammen bilden den vollständigen Bezeichner für die Methode, die intern sein können. Nehmen wir beispielsweise an das Modul `A` definiert eine Methode `Simple.Add`:

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

Modul B definiert `Fancy.AddTwice`:

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Ermöglicht darüber hinaus vorausgesetzt, die `Fancy.AddTwice` wird der Aufruf zum `SimpleAdd`. Ein Profiler kann dieser Enumerator verwenden, finden Sie in Modul B die Inline definiert alle Methoden `Simple.Add`, und das Ergebnis würde auflisten `AddTwice`.  `inlineeModuleId` Der Bezeichner des Moduls `A`, und `inlineeMethodId` ist der Bezeichner des `Simple.Add(int a, int b)`.

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

- [ICorProfilerInfo6-Schnittstelle](icorprofilerinfo6-interface.md)