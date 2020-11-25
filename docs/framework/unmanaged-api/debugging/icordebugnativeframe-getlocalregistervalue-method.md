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
ms.openlocfilehash: a90bba4a4dc9ca92ccdc4af1636d194f92fd7373
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695724"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterValue-Methode

Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das im angegebenen Register für diesen systemeigenen Frame gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `reg`  
 in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das den Wert enthält.  
  
 `cbSigBlob`  
 in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .  
  
 `pvSigBlob`  
 in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Register gespeichert ist.  
  
## <a name="remarks"></a>Hinweise  

 Die `GetLocalRegisterValue` -Methode kann entweder in einem nativen Frame oder einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
