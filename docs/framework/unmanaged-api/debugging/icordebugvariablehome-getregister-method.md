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
ms.openlocfilehash: 6cf66774209bd07426872c29c15b2225421c2b4d
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396834"
---
# <a name="icordebugvariablehomegetregister-method"></a>Icordebugvariablehome:: getregiester-Methode
Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER` und dem Basisregister für eine Variable mit dem Speicherorttyp enthält `VLT_REGISTER_RELATIVE` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRegister`  
 vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER` und das Basisregister für eine Variable mit dem Speicherorttyp angibt `VLT_REGISTER_RELATIVE` .  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode gibt die folgenden Werte zurück:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Die-Variable befindet sich in dem durch das-Argument aufgeführten Register `pRegister` .|  
|`E_FAIL`|Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [VariableLocationType-Enumeration](variablelocationtype-enumeration.md)
- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
