---
title: ICorDebugMDA-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: c4ff28ff1019b5314902a4e71f6d02b5a2fd8d70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710843"
---
# <a name="icordebugmda-interface"></a>ICorDebugMDA-Schnittstelle

Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetDescription-Methode](icordebugmda-getdescription-method.md)|Ruft eine Zeichenfolge ab, die eine Beschreibung dieses MDA enthält.|  
|[GetFlags-Methode](icordebugmda-getflags-method.md)|Ruft die diesem MDA zugeordneten Flags ab.|  
|[GetName-Methode](icordebugmda-getname-method.md)|Ruft eine Zeichenfolge ab, die den Namen dieses MDA enthält.|  
|[GetOSThreadId-Methode](icordebugmda-getosthreadid-method.md)|Ruft den Thread Bezeichner des Betriebssystems ab, auf dem dieser MDA ausgeführt wird.|  
|[GetXML-Methode](icordebugmda-getxml-method.md)|Ruft den vollständigen XML-Stream ab, der diesem MDA zugeordnet ist.|  
  
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
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
