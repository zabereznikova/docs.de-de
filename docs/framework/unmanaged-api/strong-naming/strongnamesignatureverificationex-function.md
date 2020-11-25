---
title: StrongNameSignatureVerificationEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719267"
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx-Funktion

Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszFilePath`  
 in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.  
  
 `fForceVerification`  
 [in] `true` zum Durchführen der Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen außer Kraft zu setzen. andernfalls `false` .  
  
 `pfWasVerified`  
 [out] `true` , wenn die Signatur des starken Namens überprüft wurde. andernfalls `false` . `pfWasVerified` wird auch auf festgelegt, `false` Wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  

 `true` , wenn die Überprüfung erfolgreich war. andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 `StrongNameSignatureVerificationEx` bietet eine ähnliche Funktion wie die [StrongNameSignatureVerification](strongnamesignatureverification-function.md) -Funktion. Der zweite Eingabeparameter und der Output-Parameter für `StrongNameSignatureVerificationEx` sind jedoch vom Typ `BOOLEAN` anstelle von `DWORD` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureVerificationEx-Methode](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification-Methode](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
