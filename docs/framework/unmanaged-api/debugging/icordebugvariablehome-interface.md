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
ms.openlocfilehash: 306a07450b8ae6d29875ca0cc4679390472e4d1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121043"
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome-Schnittstelle
Stellt eine lokale Variable oder ein Argument einer Funktion dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetArgumentIndex-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getargumentindex-method.md)|Ruft den Index eines Funktionsarguments ab.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getcode-method.md)|Ruft die ICorDebugCode-Instanz ab, die dieses `ICorDebugVariableHome` Objekt enthält.|  
|[GetLiveRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getliverange-method.md)|Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.|  
|[GetLocationType-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getlocationtype-method.md)|Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.|  
|[GetOffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getoffset-method.md)|Ruft den Offset aus dem Basisregister für eine Variable ab.|  
|[GetRegister-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getregister-method.md)|Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER`enthält, und das Basisregister für eine Variable mit dem Speicherorttyp `VLT_REGISTER_RELATIVE`.|  
|[GetSlotIndex-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-getslotindex-method.md)|Ruft den verwalteten Slot-Index einer lokalen Variablen ab.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Code Fragment verwendet das [ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md) -Objekt mit dem Namen `pCode4`.  
  
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
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugVariableHomeEnum-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)
