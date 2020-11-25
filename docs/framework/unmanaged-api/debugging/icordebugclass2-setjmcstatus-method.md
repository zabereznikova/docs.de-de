---
title: ICorDebugClass2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717824"
---
# <a name="icordebugclass2setjmcstatus-method"></a>ICorDebugClass2::SetJMCStatus-Methode

Legt für jede Methode der Klasse einen Wert fest, der angibt, ob es sich bei der Methode um benutzerdefinierten Code handelt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `bIsJustMyCode`  
 in Legen Sie auf fest, `true` um anzugeben, dass es sich bei der Methode um benutzerdefinierten Code handelt, andernfalls auf `false` .  
  
## <a name="remarks"></a>Hinweise  

 Ein JMC-Stepper (Just-my-Code) überspringt Nichtbenutzer definierten Code. Der benutzerdefinierte Code muss eine Teilmenge des debugfähigen Codes sein.  
  
 `SetJMCStatus` Gibt einen HRESULT-Wert von S_FALSE zurück, wenn der Wert für keine Methode festgelegt werden kann, auch wenn der Wert für alle anderen Methoden erfolgreich festgelegt wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
