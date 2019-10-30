---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod-Methode
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130382"
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
in Der Bezeichner eines Moduls, das `inlineeMethodId`definiert. Weitere Informationen finden Sie im Abschnitt Hinweise.

`inlineeMethodId`\
in Der Bezeichner einer Inline Methode. Weitere Informationen finden Sie im Abschnitt Hinweise.

`incompleteData`\
vorgenommen Ein Flag, das angibt, ob `ppEnum` alle Methoden enthält, die eine bestimmte Methode Inlining.  Weitere Informationen finden Sie im Abschnitt Hinweise.

`ppEnum`\
vorgenommen Ein Zeiger auf die Adresse eines Enumerators.

## <a name="remarks"></a>Hinweise

`inlineeModuleId` und `inlineeMethodId` bilden den vollständigen Bezeichner für die Methode, die möglicherweise Inline ist. Nehmen Sie beispielsweise an, Modul `A` definiert eine Methode `Simple.Add`:

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

und Modul B definiert `Fancy.AddTwice`:

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

Außerdem wird angenommen, dass `Fancy.AddTwice` den-Aufruf`SimpleAdd`. Ein Profiler kann diesen Enumerator verwenden, um alle in Modul B definierten Methoden zu suchen, die Inline `Simple.Add`sind, und das Ergebnis listet `AddTwice`auf.  `inlineeModuleId` ist der Bezeichner des Moduls `A`, und `inlineeMethodId` ist der Bezeichner `Simple.Add(int a, int b)`.

Wenn `incompleteData` nach der Rückgabe der Funktion true ist, enthält der Enumerator nicht alle Methoden, die eine bestimmte Methode Inlining enthalten. Dies kann vorkommen, wenn eine oder mehrere direkte oder indirekte Abhängigkeiten des Inliners-Moduls noch nicht geladen wurden. Wenn ein Profiler genaue Daten benötigt, sollte er später wiederholt werden, wenn mehr Module geladen werden, vorzugsweise bei jedem Modul Ladevorgang.

Die `EnumNgenModuleMethodsInliningThisMethod`-Methode kann verwendet werden, um Einschränkungen für das Inlining für ReJIT zu umgehen. ReJIT ermöglicht einem Profiler, die Implementierung einer Methode zu ändern und dann im Handumdrehen neuen Code zu erstellen. Beispielsweise können wir `Simple.Add` wie folgt ändern:

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

Da `Fancy.AddTwice` jedoch bereits `Simple.Add`Inline ist, weist es weiterhin das gleiche Verhalten wie zuvor auf. Um diese Einschränkung zu umgehen, muss der Aufrufer alle Methoden in allen Modulen suchen, die Inline `Simple.Add` und `ICorProfilerInfo5::RequestRejit` für jede dieser Methoden verwenden. Wenn die Methoden erneut kompiliert werden, haben Sie das neue Verhalten von `Simple.Add` anstelle des alten Verhaltens.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo6-Schnittstelle](icorprofilerinfo6-interface.md)
