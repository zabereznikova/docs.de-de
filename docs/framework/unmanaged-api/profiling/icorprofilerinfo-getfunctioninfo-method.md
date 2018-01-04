---
title: ICorProfilerInfo::GetFunctionInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17512077ef7a8ca45fa76c00f93612015948d083
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a>ICorProfilerInfo::GetFunctionInfo-Methode
Ruft die übergeordnete Klasse und die Metadaten für die angegebene Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a>Parameter  
 `functionId`  
 [in] Die ID der Funktion, für die die übergeordnete Klasse und das Metadatentoken abgerufen.  
  
 `pClassId`  
 [out] Ein Zeiger auf die übergeordnete Klasse der Funktion.  
  
 `pModuleId`  
 [out] Ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.  
  
 `pToken`  
 [out] Ein Zeiger auf das Metadatentoken für die Funktion.  
  
## <a name="remarks"></a>Hinweise  
 Der Profilercode kann Aufrufen [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) auf eine Metadatenschnittstelle für ein bestimmtes Modul zu erhalten. Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Funktion verwendet werden.  
  
 Die `ClassID` einer Funktion in einer generischen Klasse möglicherweise nicht ohne weitere Kontextinformationen für die Verwendung der Funktion erhältlich. In diesem Fall `pClassId` wird "0" sein. Zu verwendende Profilercode [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) mit einem COR_PRF_FRAME_INFO-Wert, um mehr Kontext bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
