---
title: ICoreClrDebugTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: 83afe121b6bf0de3c5542695e38b6605db7a8b6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121816"
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget-Schnittstelle
Stellt Methoden bereit, die Verweis Zählungen steuern, Prozesse aufzählen und den Arbeitsspeicher freigeben, der einem Debugger zugeordnet ist, der einem Remote Macintosh-Silverlight-Ziel zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICoreClrDebugTarget::EnumProcesses-Methode](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.|  
|[ICoreClrDebugTarget::EnumRuntimes-Methode](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|Listet die Common Language Runtime (clrs) im angegebenen Prozess auf einem Remote Computer auf.|  
|[ICoreClrDebugTarget::FreeMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|Gibt den Arbeitsspeicher frei, der von den Enumerationsmethoden in dieser Klasse zugeordnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86. dll  
  
 **.NET Framework Versionen:** 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
