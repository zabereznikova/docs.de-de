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
ms.openlocfilehash: 62b34128be99ce7750d45e6c19e26bef7fcc98c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502950"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>ICorProfilerInfo::GetModuleMetaData-Methode
Ruft eine Instanz der Metadatenschnittstelle ab, die dem angegebenen Modul zugeordnet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Parameter  
 `moduleId`  
 in Die ID des Moduls, dem die Schnittstellen Instanz zugeordnet wird.  
  
 `dwOpenFlags`  
 in Ein Wert der [CorOpenFlags](../metadata/coropenflags-enumeration.md) -Enumeration, der den Modus für das Öffnen von Manifest-Dateien angibt. Nur die `ofRead` `ofWrite` Bits, und `ofNoTransform` sind gültig.  
  
 `riid`  
 in Die Verweis-ID (GUID) der Metadatenschnittstelle, deren Instanz abgerufen wird. Eine Liste der Schnittstellen finden Sie unter [Metadatenschnittstellen](../metadata/metadata-interfaces.md) .  
  
 `ppOut`  
 vorgenommen Ein Zeiger auf die Adresse der Metadatenschnittstellen-Instanz.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie werden möglicherweise aufgefordert, die Metadaten im Lese-/Schreibmodus zu öffnen, dies führt jedoch zu einer langsameren metadatenausführung des Programms, da an den Metadaten vorgenommene Änderungen nicht wie vom Compiler optimiert werden können.  
  
 Einige Module (z. b. Ressourcen Module) haben keine Metadaten. In diesen Fällen `GetModuleMetaData` gibt einen HRESULT-Wert von S_FALSE und einen NULL-Wert in * zurück `ppOut` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerInfo-Schnittstelle](icorprofilerinfo-interface.md)
