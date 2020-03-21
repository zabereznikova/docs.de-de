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
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178443"
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
 [out] Ein Array von [CoreClrDebugProcInfo-Strukturen,](coreclrdebugprocinfo-structure.md) die die auf dem Remotecomputer ausgeführten Prozesse darstellen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Erfolg.  
  
 E_OUTOFMEMORY  
 Für `ppProcs` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Bemerkungen  
 Um den Speicher freizugeben, der von dieser Methode zugewiesen wurde, rufen Sie die [ICoreClrDebugTarget::FreeMemory-Methode](icoreclrdebugtarget-freememory-method.md) auf.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CoreClrRemoteDebuggingSchnittstellen.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1  
  
## <a name="see-also"></a>Weitere Informationen

- [ICoreClrDebugTarget-Schnittstelle](icoreclrdebugtarget-interface.md)
