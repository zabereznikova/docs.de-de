---
title: ICorProfilerInfo::GetAppDomainInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 0407b7057753f7fdee6ea6b1d05144b135b6378a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864088"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a>ICorProfilerInfo::GetAppDomainInfo-Methode
Akzeptiert eine Anwendungsdomänen-ID. Gibt den Namen einer Anwendungsdomäne und die ID des Prozesses zurück, in dem diese enthalten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a>Parameters  
 `appDomainId`  
 [in] Die ID der Anwendungsdomäne.  
  
 `cchName`  
 [in] Die Länge des `szName`-Rückgabepuffers in Zeichen.  
  
 `pcchName`  
 [out] Ein Zeiger auf die Gesamtzeichenanzahl des Namens der Anwendungsdomäne.  
  
 `szName`  
 [out] Ein vom Aufrufer bereitgestellter Breitzeichenpuffer. Wenn die Methode abgeschlossen ist, enthält `szName` den vollständigen oder teilweisen Anwendungsdomänennamen.  
  
 `pProcessId`  
 [out] Ein Zeiger auf die ID Prozesses, der die Anwendungsdomäne enthält.  
  
## <a name="remarks"></a>Hinweise  
 Nachdem diese Methode abgeschlossen ist, müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Namen der Anwendungsdomäne aufzunehmen. Vergleichen Sie zu diesem Zweck den Wert, auf den `pcchName` verweist, mit dem Wert des Parameters `cchName`. Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetAppDomainInfo` erneut auf.  
  
 Alternativ können Sie zuerst `GetAppDomainInfo` mit einem `szName`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln. Sie können die Puffergröße dann auf den Wert festlegen, der von `pcchName` zurückgegeben wurde, und `GetAppDomainInfo` erneut aufrufen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
