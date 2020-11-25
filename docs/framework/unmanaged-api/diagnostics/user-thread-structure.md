---
title: USER_THREAD-Struktur
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722894"
---
# <a name="user_thread-structure"></a>USER_THREAD-Struktur

Stellt einem Debugger Informationen zu einem Thread bereit. Weitere Informationen finden Sie unter der [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`pSidBuffer`|Adresse des Thread Puffers.|  
|`dwSidLen`|Länge des Thread Puffers in Bytes.|  
|`dwTid`|Thread-ID.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Weitere Informationen

- [SetNotifyFilter-Methode](inotifysource2-setnotifyfilter-method.md)
- [Diagnosesymbolspeicher-Strukturen](diagnostics-symbol-store-structures.md)
