---
title: ICoreClrDebugTarget::EnumRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afb31646d21ec7e15f79601f5fe83ea6ce44fa90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134677"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes-Methode
Listet die CLR-Laufzeiten (Common Language Runtime) im angegebenen Prozess auf, der auf einem Remotecomputer ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Parameter  
 `dwInternalProcessID`  
 [in] Die interne Prozess-ID des Prozesses, für den Laufzeiten aufgelistet werden sollen. Dies `m_dwInternalID` aus der entsprechenden [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).  
  
 `pcRuntimes`  
 [out] Die Anzahl der in `ppRuntimes` zurückgegebenen Laufzeiten. Dieser Wert kann 0 (null) sein.  
  
 `ppRuntimes`  
 [out] Ein Array von [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) Strukturen, die Laufzeiten darstellen, die in der remote-Zielprozess geladen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Erfolgreich.  
  
 S_FALSE  
 `dwInternalProcessID` entspricht keiner Prozess, der auf dem Computer ausgeführt wird wahrscheinlich weil der Prozess beendet wurde. `pcRuntimes` und `ppRuntimes` NULL.  
  
 E_OUTOFMEMORY  
 Für `ppRuntimes` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Um den Arbeitsspeicher freizugeben, der von dieser Methode belegt wurde, rufen Sie die [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICoreClrDebugTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
