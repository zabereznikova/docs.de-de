---
title: 'Icordebugvariablehome:: gedeffset-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711792"
---
# <a name="icordebugvariablehomegetoffset-method"></a>Icordebugvariablehome:: gedeffset-Methode

Ruft den Offset aus dem Basisregister für eine Variable ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pOffset`  
 vorgenommen Der Offset aus dem Basisregister.  
  
## <a name="return-value"></a>Rückgabewert  

 Die-Methode gibt die folgenden Werte zurück:  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`S_OK`|Die Variable befindet sich in einer Register-relativen Speicheradresse.|  
|`E_FAIL`|Die-Variable befindet sich nicht in einem Register-relativen Speicher Speicherort.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
