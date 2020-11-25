---
title: 'Icordebugvariablehome:: getlocationtype-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 3979ed19f8a61ac1fc045b83c52e23d7255ac364
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711870"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a>Icordebugvariablehome:: getlocationtype-Methode

Ruft den Typ des systemeigenen Speicher Orts der Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pLocationType`  
 vorgenommen Ein Zeiger auf den Typ des nativen Speicher Orts der Variablen.  Weitere Informationen finden Sie in der [variablelocationtype](variablelocationtype-enumeration.md) -Enumeration.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
- [VariableLocationType-Enumeration](variablelocationtype-enumeration.md)
