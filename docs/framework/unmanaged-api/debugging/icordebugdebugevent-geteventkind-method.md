---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713677"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>ICorDebugDebugEvent::GetEventKind-Methode

Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Parameter  

 pDebugEventKind  
 Ein Zeiger auf einen [cordebugdebugeventkind](cordebugdebugeventkind-enumeration.md) -Enumerationsmember, der den Ereignistyp angibt.  
  
## <a name="remarks"></a>Hinweise  

 Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.  
  
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
