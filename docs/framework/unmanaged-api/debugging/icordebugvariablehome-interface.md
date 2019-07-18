---
title: ICorDebugVariableHome-Schnittstelle
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugVariableHome
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome
helpviewer_keywords:
- ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 76f2bf3b-759f-4eed-bce7-119415b25915
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 339a0f502b7e47f7bee82a0da92185481d909e64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768868"
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome-Schnittstelle
Stellt eine lokale Variable oder ein Argument einer Funktion.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetArgumentIndex-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|Ruft den Index ein Funktionsargument ab.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|Ruft die Instanz von "ICorDebugCode", der diesen `ICorDebugVariableHome` Objekt.|  
|[GetLiveRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|Ruft ab, der systemeigenen Bereich, in dem diese Variable ist.|  
|[GetLocationType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|Ruft den Typ des systemeigenen Speicherorts für den Wert der Variablen ab.|  
|[GetOffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|Ruft den Offset aus dem Basis-Register für eine Variable ab.|  
|[GetRegister-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|Ruft ab, das Register, die eine Variable mit einem Standort enthält `VLT_REGISTER`, und registrieren Sie die Basis für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.|  
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
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugVariableHomeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
