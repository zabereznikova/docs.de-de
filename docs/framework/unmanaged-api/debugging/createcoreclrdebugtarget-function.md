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
ms.openlocfilehash: d52757f82a950c382c7c8f2162630eda7d7795e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132091"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget-Funktion
Erstellt eine Verbindung mit einem debuggerproxy, der auf einem Remote Computer ausgeführt wird, und gibt ein [icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt zurück, das zum Abfragen von laufenden Prozessen und geladenen Laufzeiten auf dem Remote Computer verwendet werden kann.  
  
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
 vorgenommen Zeiger auf einen Zeiger auf ein [icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_OUTOFMEMORY  
 Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
