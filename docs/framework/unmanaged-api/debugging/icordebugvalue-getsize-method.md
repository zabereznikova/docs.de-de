---
title: ICorDebugValue::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 9f5688ae4f76f9ddfde231aa6252d666c9152eec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731079"
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize-Methode

Ruft die Größe des "ICorDebug Value"-Objekts in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pSize`  
 vorgenommen Die Größe (in Bytes) dieses Wert Objekts.  
  
## <a name="remarks"></a>Hinweise  

 Wenn der Typ des Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.  
  
 Die `ICorDebugValue::GetSize` -Methode gibt `COR_E_OVERFLOW` für Objekte, die größer als 4 GB sind, auf 64-Bit-Plattformen zurück. Verwenden Sie stattdessen die [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) -Methode für Objekte, die größer als 4 GB sind.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetSize64-Methode](icordebugvalue3-getsize64-method.md)
