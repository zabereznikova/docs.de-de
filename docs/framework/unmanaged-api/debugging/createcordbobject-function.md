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
ms.openlocfilehash: 340d2de09562ea9b767203a7fa839cdc6b729b3b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860893"
---
# <a name="createcordbobject-function"></a>CreateCordbObject-Funktion
Erstellt eine Debugger-Schnittstelle ([ICorDebug](icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remote Prozess bereitstellt.  
  
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
 vorgenommen Zeiger auf einen Zeiger auf ein Objekt, das in eine [ICorDebug](icordebug-interface.md) -Schnittstelle umgewandelt und zurückgegeben wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.  
  
 E_INVALIDARG  
 `ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Andere Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebug](icordebug-interface.md) -Schnittstelle, die `ppCordb` in zurückgegeben wird, ist die Debugschnittstelle der obersten Ebene für alle verwalteten Debugdienste.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
