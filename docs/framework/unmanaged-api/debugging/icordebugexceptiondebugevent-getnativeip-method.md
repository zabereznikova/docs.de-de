---
title: ICorDebugExceptionDebugEvent::GetNativeIP-Methode
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: f3b29b3ceda521afe9543588af332531aa03e84e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697414"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>ICorDebugExceptionDebugEvent::GetNativeIP-Methode

Ruft den systemeigenen Anweisungszeiger für dieses Ausnahmedebugereignis ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pIP`  
 [out] Ein Zeiger auf den Anweisungszeiger für dieses Ausnahmedebugereignis. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
## <a name="remarks"></a>Hinweise  

 Die Bedeutung dieses Anweisungszeigers hängt (wie in der folgenden Tabelle gezeigt) vom Ereignistyp ab.  
  
|Ereignistyp|Bedeutung des `pStackPointer`-Werts|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Die Adresse der fehlerhaften Anweisung.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Die Code Adresse im Frame, der durch die [getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) -Methode angegeben wird, in der die Ausführung fortgesetzt wird, wenn keine Ausnahme ausgelöst wurde. Die Ausnahme kann ggf. bewirken, dass anderer Code (z. B. der Catch-Block einer nicht verursachen eine `try/catch/finally`-Klausel) in diesem Frame ausgeführt wird.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Die Code Adresse, `catch` an der die handlerausführung in dem Frame beginnt, der durch die [getstackpointer](icordebugexceptiondebugevent-getstackpointer-method.md) -Methode angegeben wird.|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pIP` ist 0.|  
  
 Der Ereignistyp ist über die [icordebugdebugevent:: geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode verfügbar.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugExceptionDebugEvent-Schnittstelle](icordebugexceptiondebugevent-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
