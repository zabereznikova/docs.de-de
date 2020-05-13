---
title: ICorDebugFunction2::GetVersionNumber-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
ms.openlocfilehash: f47263872b1baf1038a5fa9816c96e3e2569e705
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213217"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber-Methode
Ruft die Edit-und continue-Version dieser Funktion ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnVersion`  
 vorgenommen Ein Zeiger auf eine ganze Zahl, die die Versionsnummer der Funktion ist, die durch dieses ICorDebugFunction2-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Laufzeit verfolgt die Anzahl der Änderungen, die während einer Debugsitzung an den einzelnen Modulen vorgenommen wurden. Die Versionsnummer einer Funktion ist um eins größer als die Nummer der Bearbeitung, die die Funktion eingeführt hat. Die ursprüngliche Version der Funktion ist Version 1. Die Zahl wird für ein Modul jedes Mal erhöht, wenn [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) für dieses Modul aufgerufen wird. Wenn der Text einer Funktion im ersten und dritten-Vorgang ersetzt wurde `ICorDebugModule2::ApplyChanges` , `GetVersionNumber` gibt daher möglicherweise Version 1, 2 oder 4 für diese Funktion zurück, aber nicht Version 3. (Diese Funktion hätte keine Version 3.)  
  
 Die Versionsnummer wird für jedes Modul separat nachverfolgt. Wenn Sie also vier Bearbeitungen für Modul 1 und keine für Modul 2 durchführen, wird bei der nächsten Bearbeitung von Modul 1 die Versionsnummer 6 allen bearbeiteten Funktionen in Modul 1 zugewiesen. Wenn das gleiche Bearbeitungsmodul 2 verwendet, erhalten die Funktionen in Modul 2 eine Versionsnummer von 2.  
  
 Die Versionsnummer, die von der- `GetVersionNumber` Methode abgerufen wird, ist möglicherweise niedriger als die von [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).  
  
 Die [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) -Methode führt denselben Vorgang wie aus `ICorDebugFunction2::GetVersionNumber` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
