---
title: CALL_ID-Struktur
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 204c2dfbf28f95c1b8c2d2c1b757730e64a8e91d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503702"
---
# <a name="callid-structure"></a>CALL_ID-Struktur
Stellt Informationen bereit, an den Debugger zu einer Funktion, die aufgerufen wird. Finden Sie unter den [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Schnittstelle für Weitere Informationen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`szMachine`|Identifiziert den Computer, der den Aufruf ausgeführt hat.|  
|`dwPid`|Gibt den Computerprozessor an.|  
|`pUserThread`|Identifiziert den Thread, der den Aufruf ausgeführt wird.|  
|`addrStackPointer`|Gibt die Adresse der Aufrufliste.|  
|`szEntryPoint`|Gibt die Adresse des Aufrufs.|  
|`szDestinationMachine`|Identifiziert den Computer, der den Aufruf ausgeführt wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Siehe auch
- [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
