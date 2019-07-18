---
title: CorDebugExceptionObjectStackFrame-Struktur
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd2add7e96a8edaff8509563ae1846e80132001
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740098"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>CorDebugExceptionObjectStackFrame-Struktur
Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`pModule`|Ein Zeiger auf das ICorDebugModule-Objekt, für den aktuellen Frame.|  
|`ip`|Der Wert des Anweisungszeigers (EIP/RIP) für den aktuellen Frame.|  
|`methodDef`|Die Methodentoken für den aktuellen Frame.|  
|`isLastForeignExceptionFrame`|Ein Wert, der angibt, ob der Rahmen der letzte Frame in einer foreign-Ausnahme ist.|  
  
## <a name="remarks"></a>Hinweise  
 Der Aufrufer muss den Zeiger auf das Objekt ICorDebugModule freigeben, sobald es nicht mehr verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
