---
title: ICorDebugDebugEvent::GetThread-Methode
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: ca6aba7897d9e97743d29db49bd058e140f84e6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713586"
---
# <a name="icordebugdebugeventgetthread-method"></a>ICorDebugDebugEvent::GetThread-Methode

Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a>Parameter  

 ppThread  
 [out] Ein Zeiger auf die Adresse eines ICorDebugThread-Objekts, das den Thread darstellt, auf dem das Ereignis aufgetreten ist.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDebugEvent-Schnittstelle](icordebugdebugevent-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
