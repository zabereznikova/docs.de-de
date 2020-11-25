---
title: ICorDebugObjectValue::GetClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 42e5ffeeb81bc5e9a99c8ada8d58296fc9f610d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695399"
---
# <a name="icordebugobjectvaluegetclass-method"></a>ICorDebugObjectValue::GetClass-Methode

Ruft die Klasse dieses Objekt Werts ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppClass`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugClass-Objekts, das die Klasse des Objekt Werts darstellt, der durch dieses "ICorDebugObjectValue"-Objekt dargestellt wird.  
  
## <a name="remarks"></a>Hinweise  

 Die `GetClass` -Methode und die [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) -Methode geben jeweils Informationen über den Typ eines Werts zurück. beide werden durch den Generika-fähigen [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md)abgelöst.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
