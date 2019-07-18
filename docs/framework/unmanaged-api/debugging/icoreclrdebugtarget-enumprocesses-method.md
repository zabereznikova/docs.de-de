---
title: ICoreClrDebugTarget::EnumProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 301e6cc153f905bc5c15e1b526e6fb1a492a76d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774441"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>ICoreClrDebugTarget::EnumProcesses-Methode
Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pcProcs`  
 [out] Die Anzahl der in `ppProcs` zurückgegebenen Prozesse. Dieser Wert kann 0 (null) sein.  
  
 `ppProcs`  
 [out] Ein Array von [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md) Strukturen, die auf dem Remotecomputer ausgeführten Prozesse darstellen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Erfolgreich.  
  
 E_OUTOFMEMORY  
 Für `ppProcs` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
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
