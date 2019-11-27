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
ms.openlocfilehash: 0a3ec1a317fbeba2bf792378663e2fe940a8ec10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439112"
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
  
## <a name="remarks"></a>Hinweise  
 Der Profiler-Code kann [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) aufrufen, um eine Metadatenschnittstelle für ein bestimmtes Modul zu erhalten. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Funktion verwendet werden.  
  
 Die `ClassID` einer Funktion in einer generischen Klasse ist möglicherweise ohne kontextabhängige Informationen zur Verwendung der Funktion nicht zugänglich. In diesem Fall ist `pClassId` 0. Der Profiler-Code sollte [ICorProfilerInfo2:: GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) mit einem COR_PRF_FRAME_INFO Wert verwenden, um mehr Kontext bereitzustellen.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
