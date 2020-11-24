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
ms.openlocfilehash: f0188facf0b7d33e6e1ecc12921a139165f777a1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686630"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget-Funktion

Erstellt eine Verbindung mit einem debuggerproxy, der auf einem Remote Computer ausgeführt wird, und gibt ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt zurück, das zum Abfragen von laufenden Prozessen und geladenen Laufzeiten auf dem Remote Computer verwendet werden kann.  
  
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
 vorgenommen Zeiger auf einen Zeiger auf ein [icoreclrdebugtarget](icoreclrdebugtarget-interface.md) -Objekt, das erstellt wird.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_OUTOFMEMORY  
 Für `ppTarget` kann nicht genug Arbeitsspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework Versionen:** 3,5 SP1
