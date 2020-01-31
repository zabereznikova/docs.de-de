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
ms.openlocfilehash: c347346c9157fea843527c662e26ffcfba22ace4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790953"
---
# <a name="icordebugvariablehome-interface"></a>ICorDebugVariableHome-Schnittstelle
Stellt eine lokale Variable oder ein Argument einer Funktion dar.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetArgumentIndex-Methode](icordebugvariablehome-getargumentindex-method.md)|Ruft den Index eines Funktionsarguments ab.|  
|[GetCode-Methode](icordebugvariablehome-getcode-method.md)|Ruft die ICorDebugCode-Instanz ab, die dieses `ICorDebugVariableHome` Objekt enthält.|  
|[GetLiveRange-Methode](icordebugvariablehome-getliverange-method.md)|Ruft den systemeigenen Bereich ab, in dem diese Variable Live ist.|  
|[GetLocationType-Methode](icordebugvariablehome-getlocationtype-method.md)|Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.|  
|[GetOffset-Methode](icordebugvariablehome-getoffset-method.md)|Ruft den Offset aus dem Basisregister für eine Variable ab.|  
|[GetRegister-Methode](icordebugvariablehome-getregister-method.md)|Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER`enthält, und das Basisregister für eine Variable mit dem Speicherorttyp `VLT_REGISTER_RELATIVE`.|  
|[GetSlotIndex-Methode](icordebugvariablehome-getslotindex-method.md)|Ruft den verwalteten Slot-Index einer lokalen Variablen ab.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Code Fragment verwendet das [ICorDebugCode4](icordebugcode4-interface.md) -Objekt mit dem Namen `pCode4`.  
  
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
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [ICorDebugVariableHomeEnum-Schnittstelle](icordebugvariablehomeenum-interface.md)
