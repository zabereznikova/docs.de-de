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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbcf6c842e7eee55609a9ea2a25cda4360f8dc95
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739290"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget-Funktion
Erstellt eine Verbindung mit einem Debuggerproxy, die auf einem Remotecomputer ausgeführt wird, und gibt eine [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt, das zum Abfragen der ausgeführten Prozesse und geladene Laufzeitmodule auf dem Remotecomputer verwendet werden kann.  
  
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
 [out] Zeiger auf einen Zeiger auf ein [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_OUTOFMEMORY  
 Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
