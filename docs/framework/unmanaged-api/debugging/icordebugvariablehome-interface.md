---
title: ICorDebugVariableHome-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ICorDebugVariableHome
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome
helpviewer_keywords: ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea8f4033a6b0878288c49d6f6d964eb40675162d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome-Schnittstelle
Stellt eine lokale Variable oder ein Argument einer Funktion.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetArgumentIndex-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|Ruft den Index ein Funktionsargument ab.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|Ruft die "ICorDebugCode"-Instanz, die dieses enthält `ICorDebugVariableHome` Objekt.|  
|[GetLiveRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|Ruft den systemeigenen Bereich über den diese Variable aktiv ist.|  
|[GetLocationType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|Ruft den Typ des systemeigenen Speicherort der Variablen ab.|  
|[GetOffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|Ruft den Offset von der Basisregister für eine Variable ab.|  
|[GetRegister-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|Ruft die Registrierung, die eine Variable mit einem Speicherort enthält `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.|  
|[GetSlotIndex-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|Ruft den verwalteten slotindex einer lokalen Variablen ab.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Codefragment verwendet den [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) Objekt mit dem Namen `pCode4`.  
  
```cpp  
ICorDebugCode4 *pCode4 = NULL;  
pCode->QueryInterface(IID_ICorDebugCode4, &pCode4);  
  
ICorDebugVariableEnum *pVarLocEnum = NULL;  
pCode4->EnumerateVariableHomes(&pVarLocEnum);  
  
// retrieve local variables and arguments  
ULONG celt = 0;  
pVarLocEnum->GetCount(&celt);  
ICorDebugVariableHome **homes = new ICorDebugVariableHome *[celt];  
ULONG celtFetched = 0;  
pVarLocEnum->Next(celt, homes, &celtFetched);  
  
for (int i = 0; i < celtFetched; i++)  
{  
    VariableLocationType locType = VLT_INVALID;  
    homes[i].GetLocationType(&locType);  
    switch (locType)  
    {  
    case VLT_REGISTER:  
        CorDebugRegister register = 0;  
        locals[i].GetRegister(&register);  
        // now we know which register it is in  
        break;  
    case VLT_REGISTER_RELATIVE:  
        CorDebugRegister baseRegister = 0;  
        LONG offset = 0;  
        locals[i].GetRegister(&register);  
        locals[i].GetOffset(&offset);  
        // now we know the register-relative offset  
        break;  
    case VLT_INVALID:  
        // handle case where we can't access the location  
        break;  
    }  
}  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ICorDebugVariableHomeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
