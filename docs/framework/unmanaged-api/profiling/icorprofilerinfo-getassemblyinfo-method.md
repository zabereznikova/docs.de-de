---
title: ICorProfilerInfo::GetAssemblyInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAssemblyInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d4eab4a4bfbf91fd86a3742600f3383a8d374905
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>ICorProfilerInfo::GetAssemblyInfo-Methode
Akzeptiert eine Assembly-ID und gibt den Namen der Assembly und die ID ihres Manifestmoduls zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
#### <a name="parameters"></a>Parameter  
 `assemblyId`  
 [in] Der Bezeichner der Assembly.  
  
 `cchName`  
 [in] Die Länge von `szName` als Anzahl von Zeichen.   
  
 `pcchName`  
 [out] Ein Zeiger auf die Gesamtzeichenanzahl des Assemblynamens.  
  
 `szName`  
 [out] Ein vom Aufrufer bereitgestellter Breitzeichenpuffer. Bei Rückgabe der Funktion enthält er den Namen der Assembly.  
  
 `pAppDomainId`  
 [out] Ein Zeiger auf die ID der Anwendungsdomäne, die die Assembly enthält.  
  
 `pModuleId`  
 [out] Ein Zeiger auf die ID des Manifestmoduls der Assembly.  
  
## <a name="remarks"></a>Hinweise  
 Nach der Methodenrückgabe müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Namen der Assembly aufzunehmen. Vergleichen Sie hierzu den Wert, auf den `pcchName` verweist, mit dem Wert des `cchName`-Parameters. Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetAssemblyInfo` erneut auf.  
  
 Alternativ können Sie zuerst `GetAssemblyInfo` mit einem `szName`-Puffer der Länge 0 (null) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die Puffergröße dann auf Basis des Werts anpassen, der von `pcchName` zurückgegeben wurde, und `GetAssemblyInfo` erneut aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
