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
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137283"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a>ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
Ruft den Wert eines Arguments oder einer lokalen Variablen ab, von dem das niedrige Wort und das große Wort für diesen systemeigenen Frame im angegebenen Registrierungs-bzw. Speicher Speicherort gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Ein `CORDB_ADDRESS` Wert, der den Speicherbereich angibt, der das hohe Wort des Werts enthält.  
  
 `lowWordRegister`  
 in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das niedrige Wort des Werts enthält.  
  
 `cbSigBlob`  
 in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom `pvSigBlob`-Parameter verwiesen wird.  
  
 `pvSigBlob`  
 in Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Registrierungs-und Speicher Speicherort gespeichert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
