---
title: COR_ACTIVE_FUNCTION-Struktur
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
ms.openlocfilehash: cbc272070e9eb6810b34ec1f3fdc9e944c624cd3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132384"
---
# <a name="cor_active_function-structure"></a>COR_ACTIVE_FUNCTION-Struktur
Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind. Diese Struktur wird von der [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) -Methode verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pAppDomain`|Zeiger auf den Besitzer der Anwendungsdomäne des `ilOffset` Felds.|  
|`pModule`|Zeiger auf den Modul Besitzer des `ilOffset` Felds.|  
|`pFunction`|Zeiger auf den Funktions Besitzer des `ilOffset` Felds.|  
|`ilOffset`|Der MSIL-Offset (Microsoft Intermediate Language) des Frames.|  
|`flags`|Reserviert für zukünftige Erweiterbarkeit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
