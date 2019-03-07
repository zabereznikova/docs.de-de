---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abaa543299dec74d769b91ca3b21d76863624f13
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484939"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
Ruft den Wert eines Arguments oder lokale Variable, von denen das niedrige Word und das hohe Word in der angegebenen Register und den Speicherort, für diesen Frame native gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `highWordAddress`  
 [in] Ein `CORDB_ADDRESS` -Wert, die Speicheradresse aus, das hohe Word des Werts angibt.  
  
 `lowWordRegister`  
 [in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das niedrige Word des Werts enthält.  
  
 `cbSigBlob`  
 [in] Eine ganze Zahl, die die Größe der die binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.  
  
 `pvSigBlob`  
 [in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der der Typ des Werts verweist.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, die den abgerufenen Wert, der in der angegebenen registrieren und den angegebenen Speicherort gespeichert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

