---
title: CorDebugCodeInvokeKind-Aufzählung
ms.date: 03/30/2017
api_name:
- CorDebugCodeInvokeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 059e823110686a2b939c9664fa5b67e4041c3486
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740316"
---
# <a name="cordebugcodeinvokekind-enumeration"></a>CorDebugCodeInvokeKind-Aufzählung
Beschreibt, wie durch eine exportierte Funktion verwalteter Code aufgerufen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Wenn verwalteter Code durch diese Methode aufgerufen wird, muss diese von expliziten Ereignissen oder Haltepunkten später gefunden werden.<br /><br /> – oder –<br /><br /> Man kann leicht einen Teil des verwalteten Codes, der durch diese Methode aufgerufen wird, übersehen, da gibt es keine einfache Möglichkeit gibt, diese anzuhalten.<br /><br /> – oder –<br /><br /> Mit dieser Methode lässt sich verwalteter Code grundsätzlich nicht aufrufen.|  
|`CODE_INVOKE_KIND_RETURN`|Mit dieser Methode wird verwalteter Code über eine Rückgabeanweisung aufgerufen. Mit dem Verlassen wird der nächste verwaltete Code aufgerufen.|  
|`CODE_INVOKE_KIND_TAILCALL`|Mit dieser Methode wird verwalteter Code über einen Endeaufruf aufgerufen. Der verwaltete Code wird durch die Ausführung von Einzelschritten und das Überspringen von Aufrufanweisungen aufgerufen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Enumeration wird verwendet, durch die [icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) Methode zum Bereitstellen von Informationen zum schrittweisen Durchlaufen von verwaltetem Code.  
  
> [!NOTE]
>  Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
