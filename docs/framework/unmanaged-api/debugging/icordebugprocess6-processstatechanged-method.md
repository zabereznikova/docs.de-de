---
title: ICorDebugProcess6::ProcessStateChanged-Methode
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 006c81e0339a00aac14fb4f83f2bc140990bd546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732579"
---
# <a name="icordebugprocess6processstatechanged-method"></a>ICorDebugProcess6::ProcessStateChanged-Methode

Benachrichtigt [ICorDebug](icordebug-interface.md) , dass der Prozess ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a>Parameter  

 `change`  
 in Ein Member der [processstatechanged](icordebugprocess6-processstatechanged-method.md) -Enumeration.  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger ruft diese Methode auf, um [ICorDebug](icordebug-interface.md) zu benachrichtigen, dass der Prozess ausgeführt wird.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
