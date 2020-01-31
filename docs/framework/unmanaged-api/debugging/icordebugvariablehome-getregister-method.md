---
title: 'Icordebugvariablehome:: getregiester-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 396dd9c017fca6dc7037b43355ba7f726d7390ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790987"
---
# <a name="icordebugvariablehomegetregister-method"></a>Icordebugvariablehome:: getregiester-Methode
Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER`enthält, und das Basisregister für eine Variable mit dem Speicherorttyp `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pRegister`  
 vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER`angibt, und das Basisregister für eine Variable mit dem Speicherort `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode gibt die folgenden Werte zurück:  
  
|{2&gt;Wert&lt;2}|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Die Variable befindet sich in dem durch das `pRegister`-Argument aufgeführten Register.|  
|`E_FAIL`|Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [VariableLocationType-Enumeration](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
