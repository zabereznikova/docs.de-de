---
title: CreateCoreClrDebugTarget-Funktion
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 0b210f105495fa3f5595adbcb0805e1d1fb62310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179220"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget-Funktion
Erstellt eine Verbindung zu einem Debuggerproxy, der auf einem Remotecomputer ausgeführt wird, und gibt ein [ICoreClrDebugTarget-Objekt](icoreclrdebugtarget-interface.md) zurück, das zum Abfragen ausgeführter Prozesse und geladener Laufzeiten auf dem Remotecomputer verwendet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwAddress`  
 [in] IPv4-Adresse eines Remotezielcomputers.  
  
 `ppTarget`  
 [out] Zeiger auf einen Zeiger auf ein [ICoreClrDebugTarget-Objekt,](icoreclrdebugtarget-interface.md) das erstellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_OUTOFMEMORY  
 Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CoreClrRemoteDebuggingSchnittstellen.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
