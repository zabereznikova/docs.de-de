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
ms.openlocfilehash: 15485ac94ed9074baacc4fd2662a04bdcefcf1e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709322"
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
 in Ein- `CORDB_ADDRESS` Wert, der den Speicherort angibt, der das hohe Wort des Werts enthält.  
  
 `lowWordRegister`  
 in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das niedrige Wort des Werts enthält.  
  
 `cbSigBlob`  
 in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .  
  
 `pvSigBlob`  
 in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.  
  
 `ppValue`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Registrierungs-und Speicher Speicherort gespeichert ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
