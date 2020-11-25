---
title: ICorDebugStepper::Deactivate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730584"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate-Methode

Bewirkt, dass dieser icorentbugstepper den letzten Schritt Befehl abbricht, den er empfangen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Hinweise  

 Nachdem der Befehl zuletzt empfangener Schritt abgebrochen wurde, kann ein neuer Schritt Befehl ausgegeben werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
