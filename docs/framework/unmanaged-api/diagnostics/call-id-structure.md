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
ms.openlocfilehash: 8c606f67766334800444f39b115d90f65ecca13d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448592"
---
# <a name="call_id-structure"></a>CALL_ID-Struktur
Stellt einem Debugger Informationen zu einer Funktion bereit, die aufgerufen wird. Weitere Informationen finden Sie in der [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) -Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`szMachine`|Identifiziert den Computer, der den-Befehl aufruft.|  
|`dwPid`|Identifiziert den Computer Prozessor.|  
|`pUserThread`|Identifiziert den Thread, der den-Befehl ausführt.|  
|`addrStackPointer`|Gibt die Adresse der-aufrufsstapel an.|  
|`szEntryPoint`|Gibt die Adresse des Aufrufes an.|  
|`szDestinationMachine`|Identifiziert den Computer, der den-Befehl ausführt.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
