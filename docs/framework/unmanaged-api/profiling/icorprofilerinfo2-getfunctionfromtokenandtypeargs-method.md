---
title: ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionFromTokenAndTypeArgs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs
helpviewer_keywords:
- ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
- GetFunctionFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: ce8f6aa6-4ebf-4a86-b429-4bbc8af41a8f
topic_type:
- apiref
ms.openlocfilehash: 7f1276e1adeece086ca7b6791eb6e870faf4d010
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502872"
---
# <a name="icorprofilerinfo2getfunctionfromtokenandtypeargs-method"></a>ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs-Methode
Ruft den einer `FunctionID` Funktion mit dem angegebenen Metadatentoken, der Klasse und den `ClassID` Werten beliebiger Typargumente ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdMethodDef funcDef,  
    [in] ClassID classId,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] FunctionID* pFunctionID);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleID`  
 in Die ID des Moduls, in dem sich die Funktion befindet.  
  
 `funcDef`  
 in Ein `mdMethodDef` Metadatentoken, das auf die Funktion verweist.  
  
 `classId`  
 in Die ID der enthaltenden Klasse der Funktion.  
  
 `cTypeArgs`  
 in Die Anzahl der Typparameter für die angegebene Funktion. Dieser Wert muss für nicht generische Funktionen 0 (null) sein.  
  
 `typeArgs`  
 in Ein Array von- `ClassID` Werten, von denen jeder ein Argument der-Funktion ist. Der Wert von `typeArgs` kann NULL sein `cTypeArgs` , wenn auf 0 (null) festgelegt ist.  
  
 `pFunctionID`  
 vorgenommen Ein Zeiger auf die `FunctionID` der angegebenen Funktion.  
  
## <a name="remarks"></a>Bemerkungen  
 Das Aufrufen der- `GetFunctionFromTokenAndTypeArgs` Methode mit `mdMethodRef` Metadaten anstelle eines `mdMethodDef` Metadatentokens kann zu unvorhersehbaren Ergebnissen führen. Aufrufer sollten `mdMethodRef` bei der Übergabe in eine auflösen `mdMethodDef` .  
  
 Wenn die Funktion nicht bereits geladen ist, bewirkt das Aufrufen `GetFunctionFromTokenAndTypeArgs` von, dass geladen wird. Dies ist ein gefährlicher Vorgang in vielen Kontexten. Wenn Sie diese Methode beispielsweise beim Laden von Modulen oder Typen aufrufen, kann dies zu einer Endlosschleife führen, da die Laufzeit versucht, Vorgänge zirkulär zu laden.  
  
 Im Allgemeinen wird von der Verwendung von abgeraten `GetFunctionFromTokenAndTypeArgs` . Wenn Profiler an Ereignissen für eine bestimmte Funktion interessiert sind, sollten Sie die `ModuleID` und `mdMethodDef` dieser Funktion Speichern und [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) verwenden, um zu überprüfen, ob ein bestimmtes der `FunctionID` gewünschten Funktion entspricht.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
