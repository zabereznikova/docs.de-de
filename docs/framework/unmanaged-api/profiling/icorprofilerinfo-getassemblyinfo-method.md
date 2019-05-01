---
title: ICorProfilerInfo::GetAssemblyInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad4ebe4e1255ce13974063eef3d0a4feeb5dd92b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049621"
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
  
## <a name="parameters"></a>Parameter  
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
 Nach der Methodenrückgabe müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Namen der Assembly aufzunehmen. Vergleichen Sie zu diesem Zweck den Wert, auf den `pcchName` verweist, mit dem Wert des Parameters `cchName`. Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetAssemblyInfo` erneut auf.  
  
 Alternativ können Sie zuerst `GetAssemblyInfo` mit einem `szName`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die Puffergröße dann auf Basis des Werts anpassen, der von `pcchName` zurückgegeben wurde, und `GetAssemblyInfo` erneut aufrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
