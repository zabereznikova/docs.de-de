---
title: ICorProfilerInfo2::GetFunctionInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetFunctionInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type:
- apiref
ms.openlocfilehash: e44b8afe22fdb10077048dc7bc2ccb1f605edd75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727093"
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a>ICorProfilerInfo2::GetFunctionInfo2-Methode

Ruft die übergeordnete Klasse, das Metadatentoken und die `ClassID` jedes Typarguments einer Funktion ab, falls vorhanden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `funcId`  
 [in] Die ID der Funktion, für die die übergeordnete Klasse und andere Informationen abgerufen werden sollen.  
  
 `frameInfo`  
 [in] Ein `COR_PRF_FRAME_INFO`-Wert, der auf Informationen zu einem Stapelrahmen verweist.  
  
 `pClassId`  
 [out] Ein Zeiger auf die übergeordnete Klasse der Funktion.  
  
 `pModuleId`  
 [out] Ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.  
  
 `pToken`  
 [out] Ein Zeiger auf das Metadatentoken für die Funktion.  
  
 `cTypeArgs`  
 [in] Die Größe des `typeArgs`-Arrays.  
  
 `pcTypeArgs`  
 [out] Ein Zeiger auf die Gesamtzahl der `ClassID`-Werte.  
  
 `typeArgs`  
 [out] Ein Array von `ClassID`-Werten, von denen jedes die ID eines Typarguments der Funktion darstellt. Nach Rückgabe der Methode enthält `typeArgs` einige oder alle der `ClassID`-Werte.  
  
## <a name="remarks"></a>Hinweise  

 Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine [Metadatenschnittstelle](../metadata/index.md) für ein bestimmtes Modul zu erhalten. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Funktion verwendet werden.  
  
 Die Klassen-ID und die Typargumente, die über die Parameter `pClassId` und `typeArgs` zurückgegeben werden, hängen vom im Parameter `frameInfo` übergebenen Wert ab (wie in der folgenden Tabelle gezeigt).  
  
|Der Wert des Parameters `frameInfo`.|Ergebnis|  
|----------------------------------------|------------|  
|Ein `COR_PRF_FRAME_INFO`-Wert, der von einem `FunctionEnter2`-Rückruf abgerufen wurde.|Die `ClassID`, die an den Speicherort zurückgegeben wird, auf den `pClassId` verweist, sowie alle Typargumente, die im Array `typeArgs` zurückgegeben werden, sind genau.|  
|Ein `COR_PRF_FRAME_INFO`-Objekt, das aus einer anderen Quelle als einem `FunctionEnter2`-Rückruf abgerufen wurde.|Die genaue `ClassID` und Typargumente können nicht bestimmt werden. Dies bedeutet ggf., dass `ClassID` NULL ist und einige Typargumente als <xref:System.Object> zurückgegeben werden.|  
|Null|Die genaue `ClassID` und Typargumente können nicht bestimmt werden. Dies bedeutet ggf., dass `ClassID` NULL ist und einige Typargumente als <xref:System.Object> zurückgegeben werden.|  
  
 Nachdem `GetFunctionInfo2` zurückgegeben wurde, müssen Sie sicherstellen, dass der `typeArgs`-Puffer groß genug war, um alle `ClassID`-Werte aufzunehmen. Vergleichen Sie zu diesem Zweck den Wert, auf den `pcTypeArgs` verweist, mit dem Wert des Parameters `cTypeArgs`. Wenn `pcTypeArgs` auf einen Wert verweist, der größer als `cTypeArgs` geteilt durch die Größe eines `ClassID`-Werts ist, weisen Sie einen größeren `pcTypeArgs`-Puffer zu, aktualisieren Sie `cTypeArgs` mit der neuen Größe, und rufen Sie dann `GetFunctionInfo2` erneut auf.  
  
 Alternativ können Sie zuerst `GetFunctionInfo2` mit einem `pcTypeArgs`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können dann die Größe des Puffers auf den in `pcTypeArgs` zurückgegebenen Wert dividiert durch die Größe eines `ClassID`-Werts festlegen und `GetFunctionInfo2` erneut aufrufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2-Schnittstelle](icorprofilerinfo2-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
