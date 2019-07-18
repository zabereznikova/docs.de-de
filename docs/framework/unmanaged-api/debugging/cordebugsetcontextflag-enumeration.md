---
title: CorDebugSetContextFlag-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e959ce7a77ad6ceb7f2fc848193cbd9fff028279
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739620"
---
# <a name="cordebugsetcontextflag-enumeration"></a>CorDebugSetContextFlag-Enumeration
Gibt an, ob der Kontext aus dem aktiven Frame (oder Endframe) auf dem Stapel stammt oder durch das Entladen aus einem anderen Frame berechnet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|Der Kontext ist aktiven Kontext des Threads.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|Der Kontext wurde durch das Entladen aus einem anderen Frame berechnet wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CorDebugSetContextFlag` enthält Werte, mit denen, die [ICorDebugStackWalk:: SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
