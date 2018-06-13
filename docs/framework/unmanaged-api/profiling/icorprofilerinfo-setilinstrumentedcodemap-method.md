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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ecb80de1ae46b072df4bab8357e78e7a22ae298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458062"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap-Methode
Legt eine Code Map für die angegebene Funktion mithilfe der festgelegten Zuordnungseinträge der Microsoft intermediate Language (MSIL) fest.  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, Aufrufen von `SetILInstrumentedCodeMap` auf eine `FunctionID` , dass alle Instanzen dieser Funktion in der Anwendungsdomäne darstellt, die eine generische Funktion in einer bestimmten Anwendungsdomäne beeinflusst.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]  FunctionID functionId,  
    [in]  BOOL       fStartJit,  
    [in]  ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion für die die Code Map festgelegt.  
  
 `fStartJit`  
 [in] Ein boolescher Wert, der angibt, ob der Aufruf der `SetILInstrumentedCodeMap` Methode ist die erste für einen bestimmten `FunctionID`. Festgelegt `fStartJit` auf `true` im ersten Aufruf von `SetILInstrumentedCodeMap` für einen bestimmten `FunctionID`, und `false` danach.  
  
 `cILMapEntries`  
 [in] Die Anzahl der Elemente in der `cILMapEntries` Array.  
  
 `rgILMapEntries`  
 [in] Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler fügt oft Anweisungen innerhalb des Quellcodes einer Methode um Instrumentieren Ermittlungsmethode (z. B. zu benachrichtigen, wenn eine Zeile für die angegebene Quelle erreicht ist). `SetILInstrumentedCodeMap` ermöglicht einen Profiler an die neuen Speicherorte die ursprünglichen MSIL-Anweisungen zuordnen. Ein Profiler können Sie die [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) Methode, um den ursprünglichen MSIL-Offset für einen bestimmten systemeigenen Offset abrufen.  
  
 Der Debugger wird davon ausgegangen, dass jeder Alter Offset auf einen MSIL-offset innerhalb der ursprünglichen, unveränderten MSIL-Code verweist, und dass jeder neuer Offset auf den MSIL-Offset innerhalb der neuen, instrumentierten Code verweist. Die Zuordnung sollte in aufsteigender Reihenfolge sortiert werden. Beachten Sie für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten Folgendes:  
  
-   Anordnung ändern Sie instrumentierten MSIL-Code nicht.  
  
-   Entfernen Sie den ursprünglichen MSIL-Code nicht.  
  
-   Schließen Sie Einträge für die Sequenzpunkte aus der Programmdatenbankdatei (PDB), in der Zuordnung. Die Zuordnung ist nicht fehlenden Einträge interpolieren. Der folgende Code Map wird daher angenommen:  
  
     (0 alt, 0 neu)  
  
     (5 ALT, 10 neue)  
  
     (9 ALT, 20 neu)  
  
    -   Ein Alter Offset von 0, 1, 2, 3 oder 4 wird dem neuen Offset 0 zugeordnet werden.  
  
    -   Ein Alter Offset von 5, 6, 7 oder 8 wird dem neuen Offset 10 zugeordnet werden.  
  
    -   Ein Alter Offset von 9 oder höher werden neue Offset 20 zugeordnet werden.  
  
    -   Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 wird dem alten Offset 0 zugeordnet werden.  
  
    -   Ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 wird dem alten Offset 5 zugeordnet werden.  
  
    -   Ein neuer Offset von 20 oder höher wird dem alten Offset 9 zugeordnet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
