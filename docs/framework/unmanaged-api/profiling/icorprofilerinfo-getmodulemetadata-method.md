---
title: ICorProfilerInfo::GetModuleMetaData-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1663a36ab36980af709a861b3fb0666be6fecdfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607474"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData-Methode
Ruft eine Instanz der Metadaten-Schnittstelle, die das angegebene Modul zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a>Parameter  
 `moduleId`  
 [in] Die ID des Moduls, der die Schnittstelleninstanz zugeordnet werden soll.  
  
 `dwOpenFlags`  
 [in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration, der den Modus für das Öffnen von Manifestdateien angibt. Nur die `ofRead`, `ofWrite` und `ofNoTransform` Bits sind gültig.  
  
 `riid`  
 [in] Der Verweis-ID (GUID) der Metadatenschnittstelle, deren Instanz abgerufen werden. Finden Sie unter [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) eine Liste der Schnittstellen.  
  
 `ppOut`  
 [out] Ein Zeiger auf die Adresse der Instanz der Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Möglicherweise stellen Sie für die Metadaten in Lese-/Schreibmodus geöffnet werden, aber dies führt zu langsameren metadatenausführung des Programms, da Änderungen kann nicht die Metadaten wie vom Compiler optimiert werden.  
  
 Einige Module (z. B. Ressourcenmodule) verfügen über keine Metadaten. In diesen Fällen `GetModuleMetaData` gibt einen HRESULT-Wert von S_FALSE oder Null in *`ppOut`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
