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
ms.openlocfilehash: d4780242dc34f31ecd0ff0dc2c339cdaa30278a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721161"
---
# <a name="icorprofilerinfosetilinstrumentedcodemap-method"></a>ICorProfilerInfo::SetILInstrumentedCodeMap-Methode
Legt eine Code Map für die angegebene Funktion, die mit der angegebenen Microsoft intermediate Language (MSIL)-Zuordnungseinträge fest.  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, Aufrufen von `SetILInstrumentedCodeMap` auf eine `FunctionID` , dass alle Instanzen dieser Funktion in der Anwendungsdomäne darstellt, die eine generische Funktion in einer bestimmten Anwendungsdomäne auswirkt.  
  
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
 [in] Ein boolescher Wert, der angibt, ob der Aufruf der `SetILInstrumentedCodeMap` Methode ist die erste für einen bestimmten `FunctionID`. Legen Sie `fStartJit` zu `true` im ersten Aufruf von `SetILInstrumentedCodeMap` für einen angegebenen `FunctionID`, und `false` danach.  
  
 `cILMapEntries`  
 [in] Die Anzahl der Elemente in der `cILMapEntries` Array.  
  
 `rgILMapEntries`  
 [in] Ein Array von COR_IL_MAP-Strukturen, von denen jede einen MSIL-Offset angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Profiler fügt häufig die Anweisungen im Quellcode einer Methode zum Instrumentieren von dieser Methode (z. B. zu benachrichtigen, wenn eine Zeile für die angegebene Quelle erreicht wird). `SetILInstrumentedCodeMap` ermöglicht einen Profiler, die ursprünglichen MSIL-Anweisungen zu den neuen Speicherorten zuzuordnen. Ein Profiler können die [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) Methode, um den ursprünglichen MSIL-Offset für einen bestimmten Offset des systemeigenen abzurufen.  
  
 Der Debugger geht davon aus, dass jeder Alter Offset auf einen MSIL-offset innerhalb der ursprünglichen, unveränderten MSIL-Code verweist, und jeder neuer Offset auf den MSIL-Offset innerhalb der neuen, instrumentierten Code verweist. Die Zuordnung muss in aufsteigender Reihenfolge sortiert werden. Führen Sie für die schrittweise Ausführung, um ordnungsgemäß zu arbeiten die folgenden Richtlinien:  
  
-   Keine neu instrumentierten MSIL-Code an.  
  
-   Entfernen Sie den ursprünglichen MSIL-Code nicht.  
  
-   Enthalten Sie Einträge für die Sequenzpunkte über die Programmdatenbankdatei (PDB) werden in der Zuordnung. Die Zuordnung wird nicht fehlenden Einträge interpoliert. Betrachten Sie daher in der folgenden Schritte aus:  
  
     (0 alt ist, 0 neue)  
  
     (5 alt ist, 10 neue)  
  
     (9 ALT ist, 20 neue)  
  
    -   Ein Alter Offset von 0, 1, 2, 3 oder 4 wird zum neuen Offset 0 zugeordnet werden.  
  
    -   Ein Alter Offset von 5, 6, 7 oder 8 wird zum neuen Offset 10 zugeordnet werden.  
  
    -   Ein Alter Offset des 9 oder höher wird zum neuen Offset 20 zugeordnet werden.  
  
    -   Ein neuer Offset von 0, 1, 2, 3, 4, 5, 6, 7, 8 oder 9 werden alte Offset 0 zugeordnet werden.  
  
    -   Alte Offset 5 wird ein neuer Offset von 10, 11, 12, 13, 14, 15, 16, 17, 18 oder 19 zugeordnet werden.  
  
    -   Ein neuer Offset von 20 oder höher werden alte Offset 9 zugeordnet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
