---
title: ICorDebugExceptionDebugEvent::GetNativeIP-Methode
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2455e52e46edd7fc8d4d6e8b003d3ebfd87ea07f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085830"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>ICorDebugExceptionDebugEvent::GetNativeIP-Methode
Ruft den systemeigenen Anweisungszeiger für dieses Ausnahmedebugereignis ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|[MANAGED_EXCEPTION_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Die Adresse der fehlerhaften Anweisung.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Die Codeadresse im Frame angegeben wird, durch die [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) Methode, in dem die Ausführung fortgesetzt würde, wenn keine Ausnahme ausgelöst worden wäre. Die Ausnahme kann ggf. bewirken, dass anderer Code (z. B. der Catch-Block einer nicht verursachen eine `try/catch/finally`-Klausel) in diesem Frame ausgeführt wird.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|Der Codeadresse `catch` Handler Ausführung wird gestartet, in dem Frame, angegeben durch die [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) Methode.|  
|[MANAGED_EXCEPTION_UNHANDLED](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|`pIP` ist 0.|  
  
 Der Ereignistyp ist verfügbar, aus der [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugExceptionDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
