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
ms.openlocfilehash: ece5bd5373fed1a10e6592ff884e98b614e7991d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715989"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|Wenn verwalteter Code durch diese Methode aufgerufen wird, muss diese von expliziten Ereignissen oder Haltepunkten später gefunden werden.<br /><br /> – oder –<br /><br /> Man kann leicht einen Teil des verwalteten Codes, der durch diese Methode aufgerufen wird, übersehen, da gibt es keine einfache Möglichkeit gibt, diese anzuhalten.<br /><br /> – oder –<br /><br /> Mit dieser Methode lässt sich verwalteter Code grundsätzlich nicht aufrufen.|  
|`CODE_INVOKE_KIND_RETURN`|Mit dieser Methode wird verwalteter Code über eine Rückgabeanweisung aufgerufen. Mit dem Verlassen wird der nächste verwaltete Code aufgerufen.|  
|`CODE_INVOKE_KIND_TAILCALL`|Mit dieser Methode wird verwalteter Code über einen Endeaufruf aufgerufen. Der verwaltete Code wird durch die Ausführung von Einzelschritten und das Überspringen von Aufrufanweisungen aufgerufen.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Enumeration wird von der [ICorDebugProcess6:: getexportstepinfo](icordebugprocess6-getexportstepinfo-method.md) -Methode verwendet, um Informationen über das Durchlaufen von verwaltetem Code bereitzustellen.  
  
> [!NOTE]
> Diese Enumeration ist nur für die Verwendung in .NET Native-Debugszenarien vorgesehen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
