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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6875ce0e7ae4cefa9b0c8abaded0dd4535bdf838
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740826"
---
# <a name="coractivefunction-structure"></a>COR_ACTIVE_FUNCTION-Struktur
Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind. Diese Struktur wird verwendet, durch die [ICorDebugThread2:: GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) Methode.  
  
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
|`pAppDomain`|Zeiger auf den Besitzer des der `ilOffset` Feld.|  
|`pModule`|Zeiger auf die modulbesitzer, der die `ilOffset` Feld.|  
|`pFunction`|Zeiger zum Inhaber der Funktion der `ilOffset` Feld.|  
|`ilOffset`|Der Microsoft intermediate Language (MSIL)-Offset des Frames.|  
|`flags`|Reserviert für zukünftige Erweiterbarkeit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
