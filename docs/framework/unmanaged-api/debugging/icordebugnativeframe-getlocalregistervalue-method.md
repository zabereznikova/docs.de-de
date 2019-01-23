---
title: ICorDebugNativeFrame::GetLocalRegisterValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9794a44bfb0bd1b4739689359832ba8500c6e2ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539609"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterValue-Methode
Ruft den Wert eines Arguments oder einer lokalen Variablen, die im angegebenen Register für diesen Frame native gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `reg`  
 [in] Der Wert der "CorDebugRegister"-Enumeration, die die Registrierung mit dem Wert angibt.  
  
 `cbSigBlob`  
 [in] Eine ganze Zahl, die die Größe der die binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.  
  
 `pvSigBlob`  
 [in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der der Typ des Werts verweist.  
  
 `ppValue`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, die den abgerufenen Wert, der im angegebenen Register gespeichert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetLocalRegisterValue` Methode kann verwendet werden, entweder in einem nativen Rahmen oder eine just-in-Time (JIT)-kompilierten Rahmen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

