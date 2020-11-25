---
title: ICorDebugObjectValue::IsValueClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
ms.openlocfilehash: 7b637889986425767fd7e1166c73df3301075422
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695282"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a>ICorDebugObjectValue::IsValueClass-Methode

Ruft einen Wert ab, der angibt, ob dieser Objektwert ein Werttyp ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbIsValueClass`  
 vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn der Objektwert, der durch diesen "ICorDebugObjectValue" dargestellt wird, ein Werttyp anstelle eines Verweis Typs ist; andernfalls ist der Wert `pbIsValueClass` `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
