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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497170"
---
# <a name="icordebugfunction2getversionnumber-method"></a>ICorDebugFunction2::GetVersionNumber-Methode
Ruft die bearbeiten und Fortfahren-Version dieser Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pnVersion`  
 [out] Ein Zeiger auf eine ganze Zahl, die Versionsnummer der Funktion, die von diesem ICorDebugFunction2-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Common Language Runtime behält den Überblick über die Anzahl der Änderungen, die jedes Modul während einer Debugsitzung stattgefunden haben. Die Versionsnummer einer Funktion ist eine mehr als die Anzahl der Bearbeitung, die die Funktion eingeführt. Ursprüngliche Version der Funktion ist die Version 1. Jedes Mal die Anzahl für ein Modul erhöht [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) für das Modul aufgerufen wird. Daher, wenn in der ersten und dritten Aufruf einer Funktion Text ersetzt wurde `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` möglicherweise Version 1, 2 oder 4 für diese Funktion, jedoch nicht Version 3 zurück. (Diese Funktion müssten keine Version 3.)  
  
 Die Versionsnummer wird für jedes Modul separat nachverfolgt. Also wenn Sie vier Änderungen auf die Modul1 und keine in Module2 ausführen, wird die nächste Bearbeitung Modul 1 eine Versionsnummer von 6 alle bearbeiteten Funktionen im Modul1 zuweisen. Wenn es sich bei dem Bearbeitungsvorgang Module2, erhalten die Funktionen im Module2 eine Versionsnummer von 2.  
  
 Die Versionsnummer abgerufen, indem die `GetVersionNumber` Methode ist möglicherweise niedriger als die von [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 Die [ICorDebugCode:: GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) Methode führt den gleichen Vorgang wie `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
