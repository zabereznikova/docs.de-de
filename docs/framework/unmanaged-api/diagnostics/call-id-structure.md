---
title: CALL_ID-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CALL_ID
api_location: diasymreader.dll
api_type: COM
f1_keywords: CALL_ID
helpviewer_keywords: CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71fd69cbcced1440839b9eedf8fbe3d8f5b90646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="callid-structure"></a>CALL_ID-Struktur
Enthält Informationen für einen Debugger zu einer Funktion, die aufgerufen wird. Finden Sie unter der [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) Schnittstelle für Weitere Informationen.  
  
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
|`dwPid`|Identifiziert den Computerprozessor.|  
|`pUserThread`|Identifiziert den Thread, der den Aufruf ausgeführt wird.|  
|`addrStackPointer`|Gibt die Adresse der Aufrufliste.|  
|`szEntryPoint`|Gibt die Adresse des Aufrufs.|  
|`szDestinationMachine`|Identifiziert den Computer, der den Aufruf ausgeführt wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Siehe auch  
 [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
