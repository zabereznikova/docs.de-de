---
title: COR_DEBUG_STEP_RANGE-Struktur
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: 206e4fb232f4786a76525d24aa379b25d6d2f71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099343"
---
# <a name="cor_debug_step_range-structure"></a>COR_DEBUG_STEP_RANGE-Struktur
Enthält die Offsetinformationen für einen Codebereich.  
  
 Diese Struktur wird von der [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) -Methode verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`startOffset`|Der Offset vom Anfang des Bereichs.|  
|`endOffset`|Der Offset des Endes des Bereichs.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StepRange-Methode](icordebugstepper-steprange-method.md)
- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
