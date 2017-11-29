---
title: "CorDebugCodeInvokePurpose-Aufzählung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInvokePurpose
api_location: mscordbi.dll
api_type: COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41938a11d7d92fd728772aa45bd8e97f137e5d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>CorDebugCodeInvokePurpose-Aufzählung
Beschreibt, warum durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Keine oder unbekannt.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Der verwaltete Code führt alle verwalteten Einstiegspunkte (z. B. umgekehrte p-invoke-Punkte) auf. Sämtliche detailliertere Zwecke sind in der Laufzeit unbekannt.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Der verwaltete Code führt einen statischen Konstruktor aus.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Der verwaltete Code führt die Implementierung für eine bestimmte Schnittstellenmethode aus, die aufgerufen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird verwendet, durch die [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) -Methode zum Bereitstellen von Informationen zum schrittweisen Durchlaufen von verwaltetem Code.  
  
> [!NOTE]
>  Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarios vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
