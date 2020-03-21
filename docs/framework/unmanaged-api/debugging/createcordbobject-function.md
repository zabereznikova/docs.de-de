---
title: CreateCordbObject-Funktion
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179232"
---
# <a name="createcordbobject-function"></a>CreateCordbObject-Funktion
Erstellt eine Debuggerschnittstelle ([ICorDebug](icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iDebuggerVersion`  
 [in] Debuggerversion des Zielprozesses. Dieser Parameter muss CorDebugVersion_2_0 für das Remotedebuggen sein.  
  
 `ppCordb`  
 [out] Zeiger auf einen Zeiger auf ein Objekt, das in eine [ICorDebug-Schnittstelle](icordebug-interface.md) zurückgeworfen und zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_INVALIDARG  
 `ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Bemerkungen  
 Die [ICorDebug-Schnittstelle,](icordebug-interface.md) `ppCordb` die zurückgegeben wird, ist die Debugging-Schnittstelle der obersten Ebene für alle verwalteten Debugdienstdienste.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** CoreClrRemoteDebuggingSchnittstellen.h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
