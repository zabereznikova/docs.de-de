---
title: ICorProfilerInfo::SetILInstrumentedCodeMap-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerInfo::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetILInstrumentedCodeMap method [.NET Framework profiling]
ms.assetid: bce1dcf8-b4ec-4e73-a917-f2df1ad49c8a
topic_type:
- apiref
ms.openlocfilehash: 99e473268fd0d5bb8ce120b97576277949b86508
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868996"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap-Methode

Legt einen Code Map für die angegebene Funktion mithilfe der angegebenen MSIL (Microsoft Intermediate Language)-Zuordnungs Einträge fest.

> [!NOTE]
> In der .NET Framework Version 2,0 wirkt sich das Aufrufen von `SetILInstrumentedCodeMap` auf einem `FunctionID`, das eine generische Funktion in einer bestimmten Anwendungsdomäne darstellt, auf alle Instanzen dieser Funktion in der Anwendungsdomäne aus.

## <a name="syntax"></a>Syntax

```cpp
HRESULT SetILInstrumentedCodeMap(
    [in]  FunctionID functionId,
    [in]  BOOL       fStartJit,
    [in]  ULONG      cILMapEntries,
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);
```

## <a name="parameters"></a>Parameters

`functionId`\
in Die ID der Funktion, für die die Code Map festgelegt werden soll.

`fStartJit`\
in Ein boolescher Wert, der angibt, ob der aufzurufende `SetILInstrumentedCodeMap`-Methode der erste für eine bestimmte `FunctionID`ist. Legen Sie `fStartJit` auf `true` im ersten `SetILInstrumentedCodeMap` für eine angegebene `FunctionID`und `false` danach fest.

`cILMapEntries`\
in Die Anzahl der Elemente im `cILMapEntries` Array.

`rgILMapEntries`\
in Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.

## <a name="remarks"></a>Hinweise

Ein Profiler fügt häufig Anweisungen innerhalb des Quellcodes einer Methode ein, um diese Methode zu instrumentieren (z. b. um zu benachrichtigen, wenn eine bestimmte Quellzeile erreicht ist). `SetILInstrumentedCodeMap` ermöglicht einem Profiler, die ursprünglichen MSIL-Anweisungen ihren neuen Speicherorten zuzuordnen. Ein Profiler kann die [ICorProfilerInfo:: GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md) -Methode verwenden, um den ursprünglichen MSIL-Offset für einen angegebenen systemeigenen Offset zu erhalten.

Der Debugger geht davon aus, dass jeder alte Offset in dem ursprünglichen, nicht geänderten MSIL-Code auf einen MSIL-Offset verweist und dass jeder neue Offset auf den MSIL-Offset innerhalb des neuen, instrumentierten Codes verweist. Die Zuordnung sollte in steigender Reihenfolge sortiert werden. Befolgen Sie die folgenden Richtlinien, um die ordnungsgemäße Ausführung von Schritt zu

- Instrumentierte MSIL-Code nicht neu anordnen.

- Entfernen Sie den ursprünglichen MSIL-Code nicht.

- Fügen Sie Einträge für alle Sequenz Punkte aus der Programm Datenbankdatei (PDB) in die Zuordnung ein. Fehlende Einträge werden von der Zuordnung nicht interpolieren. Bei der folgenden Karte:

  (0 alt, 0 neu)

  (5 alt, 10 neu)

  (9 alte, 20 neue)

  - Der alte Offset 0, 1, 2, 3 oder 4 wird dem neuen Offset 0 zugeordnet.

  - Der alte Offset 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet.

  - Ein Alter Offset von 9 oder höher wird dem neuen Offset 20 zugeordnet.

  - Der neue Offset 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet.

  - Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet.

  - Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet.

In den .NET Framework 3,5 und früheren Versionen weisen Sie das `rgILMapEntries` Array zu, indem Sie die [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) -Methode aufrufen. Da die Laufzeit den Besitz dieses Speichers übernimmt, sollte der Profiler nicht versuchen, ihn freizugeben.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorProf.idl, CorProf.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
