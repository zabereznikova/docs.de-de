---
title: ICorDebugExceptionDebugEvent::GetNativeIP-Methode
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 82dc892f3081c9f33ff7a2f363c326091f7cf039
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976030"
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
 [out] Ein Zeiger auf den Anweisungszeiger für dieses Ausnahmedebugereignis. Weitere Informationen finden Sie im Abschnitt zu den Hinweisen.  
  
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
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugExceptionDebugEvent-Schnittstelle](icordebugexceptiondebugevent-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
