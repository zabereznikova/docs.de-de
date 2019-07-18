---
title: CorDebugInternalFrameType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1dcbd8bb566331a6a2d4217eeec0441fbd3e6ff6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739861"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType-Enumeration
Identifiziert den Stapelrahmentyp. Diese Enumeration wird verwendet, durch die [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Ein NULL-Wert. Die `ICorDebugInternalFrame::GetFrameType` Methode gibt diesen Wert nie zurück.|  
|`STUBFRAME_M2U`|Ein Stub verwalteten zum nicht verwalteten Frame.|  
|`STUBFRAME_U2M`|Ein Stub nicht verwalteten zu verwalteten Frame.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Ein Übergang zwischen Anwendungsdomänen.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Der Aufruf einer einfachen Methode.|  
|`STUBFRAME_FUNC_EVAL`|Der Anfang der funktionsauswertung.|  
|`STUBFRAME_INTERNALCALL`|Einen internen Aufruf in der common Language Runtime.|  
|`STUBFRAME_CLASS_INIT`|Der Anfang der Initialisierung einer Klasse.|  
|`STUBFRAME_EXCEPTION`|Eine Ausnahme, die ausgelöst wird.|  
|`STUBFRAME_SECURITY`|Ein Frame, der für die Codezugriffssicherheit verwendet wird.|  
|`STUBFRAME_JIT_COMPILATION`|Die Laufzeit ist eine Methode JIT-Kompilierung.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
