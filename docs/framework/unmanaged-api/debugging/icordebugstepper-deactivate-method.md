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
ms.openlocfilehash: 1d75897e00c36bd5c484e837ee68e54443168e77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131756"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate-Methode
Bewirkt, dass dieser icorentbugstepper den letzten Schritt Befehl abbricht, den er empfangen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Nachdem der Befehl zuletzt empfangener Schritt abgebrochen wurde, kann ein neuer Schritt Befehl ausgegeben werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
