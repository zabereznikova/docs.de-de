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
ms.openlocfilehash: 4a65a98ee04c3870dae2f49b3da2a8e72b1ffae4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795831"
---
# <a name="cordebuginternalframetype-enumeration"></a>CorDebugInternalFrameType-Enumeration
Identifiziert den Stapelrahmentyp. Diese Enumeration wird von der [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) -Methode verwendet.  
  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Ein NULL-Wert. Die `ICorDebugInternalFrame::GetFrameType` -Methode gibt diesen Wert nie zurück.|  
|`STUBFRAME_M2U`|Ein verwalteter-zu-nicht verwalteter Stub-Frame.|  
|`STUBFRAME_U2M`|Ein nicht verwalteter zu verwalteter Stub-Frame.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Ein Übergang zwischen Anwendungs Domänen.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Ein Lightweight-Methoden Aufruf.|  
|`STUBFRAME_FUNC_EVAL`|Der Anfang der Funktions Auswertung.|  
|`STUBFRAME_INTERNALCALL`|Ein interner-Rückruf für die Common Language Runtime.|  
|`STUBFRAME_CLASS_INIT`|Der Anfang einer Klassen Initialisierung.|  
|`STUBFRAME_EXCEPTION`|Eine Ausnahme, die ausgelöst wird.|  
|`STUBFRAME_SECURITY`|Ein Frame, der für die Code Zugriffssicherheit verwendet wird.|  
|`STUBFRAME_JIT_COMPILATION`|Die Laufzeit ist eine JIT-Kompilierung einer Methode.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
