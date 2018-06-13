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
ms.openlocfilehash: 44f220f12f72ca8d0be6a9fc50b363c9bccb85fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417588"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
Ruft den Wert eines Arguments oder einer lokalen Variablen, von denen die niedrige Word und hohe Word in den angegebenen Register und die Speicheradresse, bzw. für diese systemeigenen Rahmen gespeichert sind.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `highWordAddress`  
 [in] Ein `CORDB_ADDRESS` Wert, der angibt, die Speicheradresse, die das hohe Word des Werts enthält.  
  
 `lowWordRegister`  
 [in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das niedrige Word des Werts enthält.  
  
 `cbSigBlob`  
 [in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.  
  
 `pvSigBlob`  
 [in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die den abgerufenen Wert, der in der angegebenen Register und den angegebenen Speicherort gespeichert ist darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
