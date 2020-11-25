---
title: CorDebugMDAFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: 1bb99503481d917d41ae00a5ef73c8fa59e2a999
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696452"
---
# <a name="cordebugmdaflags-enumeration"></a>CorDebugMDAFlags-Enumeration

Gibt den Status des Threads an, auf dem der Assistent für verwaltetes Debuggen (MDA) ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|Der Thread, in dem der MDA ausgelöst wurde, wurde seit dem Auslösen des MDA zurückgezogen.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn die-aufrufsstapel nicht mehr beschreibt, wo der MDA ursprünglich ausgelöst wurde, wird der Thread als *abgerutscht* angesehen. Dies ist ein ungewöhnlicher Umstand, der durch die Ausführung eines ungültigen Vorgangs durch den Thread beim Beenden verursacht wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
