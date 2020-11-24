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
ms.openlocfilehash: 093f49508e8e96a4003f1aab8eed59e2fd196ba9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679272"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes-Methode

Listet die CLR-Laufzeiten (Common Language Runtime) im angegebenen Prozess auf, der auf einem Remotecomputer ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>Parameter  

 `dwInternalProcessID`  
 [in] Die interne Prozess-ID des Prozesses, für den Laufzeiten aufgelistet werden sollen. Dies erfolgt über `m_dwInternalID` die entsprechende [coreclrdebugprocinfo](coreclrdebugprocinfo-structure.md).  
  
 `pcRuntimes`  
 [out] Die Anzahl der in `ppRuntimes` zurückgegebenen Laufzeiten. Dieser Wert kann 0 (null) sein.  
  
 `ppRuntimes`  
 vorgenommen Ein Array von [coreclrdebugruntimeingefo](coreclrdebugruntimeinfo-structure.md) -Strukturen, die die Laufzeiten darstellen, die im Remote Ziel Prozess geladen wurden.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK  
 Erfolg.  
  
 S_FALSE  
 `dwInternalProcessID` entspricht keinem auf dem Computer ausgeführten Prozess; wahrscheinlich wurde der Prozess beendet. `pcRuntimes` und `ppRuntimes` sind null.  
  
 E_OUTOFMEMORY  
 Für `ppRuntimes` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Hinweise  

 Um den von dieser Methode belegten Arbeitsspeicher freizugeben, müssen Sie die [icoreclrdebugtarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) -Methode aufrufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework Versionen:** 3,5 SP1  
  
## <a name="see-also"></a>Weitere Informationen

- [ICoreClrDebugTarget-Schnittstelle](icoreclrdebugtarget-interface.md)
