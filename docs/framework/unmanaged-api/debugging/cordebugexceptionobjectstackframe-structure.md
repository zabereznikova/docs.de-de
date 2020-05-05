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
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795923"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`pModule`|Ein Zeiger auf das ICorDebug Module-Objekt für den aktuellen Frame.|  
|`ip`|Der Wert des Anweisungs Zeigers (EIP/RIP) für den aktuellen Frame.|  
|`methodDef`|Das Methoden Token für den aktuellen Frame.|  
|`isLastForeignExceptionFrame`|Ein Wert, der angibt, ob der Frame der letzte Frame in einer fremd Ausnahme ist.|  
  
## <a name="remarks"></a>Hinweise  
 Der Aufrufer muss den Zeiger auf das icorentbugmodule-Objekt freigeben, wenn er nicht mehr verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
