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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bcd7bfb52cadf740d8fe3cb92a09b071f530b7ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417400"
---
# <a name="icordebugstepperdeactivate-method"></a>ICorDebugStepper::Deactivate-Methode
Bewirkt, dass dieser ICorDebugStepper, mit dem letzten Schrittbefehl "Abbrechen", den empfangen wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein neuer Schrittbefehl kann ausgegeben werden, nachdem der zuletzt empfangenen Schrittbefehl abgebrochen wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
