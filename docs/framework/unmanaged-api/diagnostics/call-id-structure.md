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
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420629"
---
# <a name="call_id-structure"></a>CALL_ID-Struktur
Stellt einem Debugger Informationen zu einer Funktion bereit, die aufgerufen wird. Weitere Informationen finden Sie in der [INotifySink2](inotifysink2-interface.md) -Schnittstelle.  
  
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Siehe auch

- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [Diagnosesymbolspeicher-Strukturen](diagnostics-symbol-store-structures.md)
