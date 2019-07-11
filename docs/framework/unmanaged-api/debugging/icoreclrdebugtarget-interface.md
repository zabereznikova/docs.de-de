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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5a3d06f72ed7163a414ef12e9bec650d8b20783
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774285"
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget-Schnittstelle
Bietet Methoden, die einen Zähler zu steuern, Auflisten von Prozessen und einen Debugger, der mit einem Remoteziel für Macintosh Silverlight verknüpft zugeordneten Arbeitsspeicher freizugeben.  
  
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
|[ICoreClrDebugTarget::EnumRuntimes-Methode](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|Listet die common Language Runtimes (Runtime) in den angegebenen Prozess auf einem Remotecomputer befindet.|  
|[ICoreClrDebugTarget::FreeMemory-Methode](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|Gibt den Arbeitsspeicher frei, der von der Enumerationsmethoden in dieser Klasse zugeordnet ist.|  
  
## <a name="remarks"></a>Hinweise  
 Derzeit wird diese Funktion unterstützt, nur für das Debuggen ein Silverlight-Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
