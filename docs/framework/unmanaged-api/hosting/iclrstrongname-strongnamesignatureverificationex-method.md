---
title: ICLRStrongName::StrongNameSignatureVerificationEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: 5bd985a6870ae6f4cc2302b6a11e8e139180d839
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503990"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>ICLRStrongName::StrongNameSignatureVerificationEx-Methode
Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
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
 [out] `true` , wenn die Signatur des starken Namens überprüft wurde. andernfalls `false` . `pfWasVerified`wird auch auf festgelegt, `false` Wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Überprüfung erfolgreich war. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Bemerkungen  
 Die [ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) -Methode bietet eine ähnliche Funktion wie die [ICLRStrongName:: StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) -Methode. Der zweite Eingabeparameter und der Output-Parameter für [ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) sind jedoch vom Typ `BOOLEAN` anstelle von `DWORD` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [StrongNameSignatureVerification-Methode](iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
