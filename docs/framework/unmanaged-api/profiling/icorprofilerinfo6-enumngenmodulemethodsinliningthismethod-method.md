---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 8ed3f305deceacb976aeff994db1588f9e1ce1fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495527"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode

Gibt einen Enumerator für alle Methoden zurück, die in einem angegebenen ngen-Modul definiert sind, und Inline eine angegebene Methode.

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
in Der Bezeichner eines ngen-Moduls.

`inlineeModuleId`\
in Der Bezeichner eines Moduls, das definiert `inlineeMethodId` . Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.

`inlineeMethodId`\
in Der Bezeichner einer Inline Methode. Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.

`incompleteData`\
vorgenommen Ein Flag, das angibt, ob `ppEnum` alle Methoden enthält, die eine bestimmte Methode Inlining.  Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.

`ppEnum`\
vorgenommen Ein Zeiger auf die Adresse eines Enumerators.

## <a name="remarks"></a>Bemerkungen

`inlineeModuleId`und `inlineeMethodId` bilden den vollständigen Bezeichner für die Methode, die möglicherweise Inline ist. Nehmen Sie beispielsweise an, das Modul `A` definiert eine Methode `Simple.Add` :

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

und Modul B definiert Folgendes `Fancy.AddTwice` :

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Außerdem wird davon ausgegangen, dass den-Befehl `Fancy.AddTwice` in den Zeilen umgibt `SimpleAdd` . Ein Profiler kann mit diesem Enumerator alle in Modul B definierten Methoden suchen, die Inline `Simple.Add` sind, und das Ergebnis würde aufzählen `AddTwice` .  `inlineeModuleId`der Bezeichner des Moduls `A` , und `inlineeMethodId` ist der Bezeichner von `Simple.Add(int a, int b)` .

Wenn den Wert `incompleteData` true hat, nachdem die Funktion zurückgegeben wurde, enthält der Enumerator nicht alle Methoden, die eine bestimmte Methode Inlining enthalten. Dies kann vorkommen, wenn eine oder mehrere direkte oder indirekte Abhängigkeiten des Inliners-Moduls noch nicht geladen wurden. Wenn ein Profiler genaue Daten benötigt, sollte er später wiederholt werden, wenn mehr Module geladen werden, vorzugsweise bei jedem Modul Ladevorgang.

Die- `EnumNgenModuleMethodsInliningThisMethod` Methode kann verwendet werden, um Einschränkungen beim Inlining für ReJIT zu umgehen. ReJIT ermöglicht einem Profiler, die Implementierung einer Methode zu ändern und dann im Handumdrehen neuen Code zu erstellen. Beispielsweise können wir `Simple.Add` wie folgt ändern:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Da jedoch `Fancy.AddTwice` bereits Inline ist `Simple.Add` , weist es weiterhin das gleiche Verhalten wie zuvor auf. Um diese Einschränkung zu umgehen, muss der Aufrufer alle Methoden in allen Modulen suchen, die Inline sind `Simple.Add` und für `ICorProfilerInfo5::RequestRejit` jede dieser Methoden verwendet werden. Wenn die Methoden erneut kompiliert werden, verfügen Sie über das neue Verhalten von `Simple.Add` anstelle des alten Verhaltens.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo6-Schnittstelle](icorprofilerinfo6-interface.md)
