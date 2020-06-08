---
title: ICorProfilerInfo::GetFunctionInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
ms.openlocfilehash: e7193526bb0da1d28da4bf6bde108fc4d3fba273
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503015"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a>ICorProfilerInfo::GetFunctionInfo-Methode
Ruft die übergeordnete Klasse und das Metadatentoken für die angegebene Funktion ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a>Parameter  
 `functionId`  
 in Die ID der Funktion, für die die übergeordnete Klasse und das Metadatentoken zu erhalten sind.  
  
 `pClassId`  
 [out] Ein Zeiger auf die übergeordnete Klasse der Funktion.  
  
 `pModuleId`  
 [out] Ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.  
  
 `pToken`  
 [out] Ein Zeiger auf das Metadatentoken für die Funktion.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine Metadatenschnittstelle für ein bestimmtes Modul zu erhalten. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Funktion verwendet werden.  
  
 Die einer `ClassID` Funktion einer generischen Klasse kann nicht ohne kontextabhängige Informationen zur Verwendung der Funktion nicht verwendet werden. In diesem Fall ist 0 (null) `pClassId` . Der Profiler-Code sollte [ICorProfilerInfo2:: GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) mit einem COR_PRF_FRAME_INFO Wert verwenden, um mehr Kontext bereitzustellen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
