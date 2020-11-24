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
ms.openlocfilehash: 62055a98197f5f8bd4cfc02e99891b83ef6341e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680293"
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
  
## <a name="parameters"></a>Parameter  

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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
- [Profilerstellungsschnittstellen](profiling-interfaces.md)
- [Profilerstellung](index.md)
