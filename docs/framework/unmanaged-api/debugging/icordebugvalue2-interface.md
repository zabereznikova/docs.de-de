---
title: ICorDebugValue2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: 7aca5fcb5a55331756b4f98c08eb46fc4db1e289
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720333"
---
# <a name="icordebugvalue2-interface"></a>ICorDebugValue2-Schnittstelle

Erweitert die ICorDebugValue-Schnittstelle, um die Unterstützung von ICorDebugType-Objekten bereitzustellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetExactType-Methode](icordebugvalue2-getexacttype-method.md)|Ruft einen Schnittstellen Zeiger auf ein- `ICorDebugType` Objekt ab, das den <xref:System.Type> dieses Werts darstellt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)

- [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)
