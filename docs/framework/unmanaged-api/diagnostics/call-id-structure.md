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
ms.openlocfilehash: 3f41dd969e25f7a42308ff0b7b2d617344284b38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725247"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`szMachine`|Identifiziert den Computer, der den-Befehl aufruft.|  
|`dwPid`|Identifiziert den Computer Prozessor.|  
|`pUserThread`|Identifiziert den Thread, der den-Befehl ausführt.|  
|`addrStackPointer`|Gibt die Adresse der-aufrufsstapel an.|  
|`szEntryPoint`|Gibt die Adresse des Aufrufes an.|  
|`szDestinationMachine`|Identifiziert den Computer, der den-Befehl ausführt.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [INotifySink2-Schnittstelle](inotifysink2-interface.md)
- [Diagnosesymbolspeicher-Strukturen](diagnostics-symbol-store-structures.md)
