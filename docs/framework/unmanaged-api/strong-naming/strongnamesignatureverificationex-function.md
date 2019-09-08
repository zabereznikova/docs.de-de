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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798918"
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
 in , um eine Überprüfung durchzuführen, auch wenn es erforderlich ist, Registrierungs Einstellungen `false`zu überschreiben, andernfalls. `true`  
  
 `pfWasVerified`  
 vorgenommen `true` ,`false`wenn die starke namens Signatur überprüft wurde, andernfalls. `pfWasVerified`wird auch auf fest `false` gelegt, wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Überprüfung erfolgreich war. `false`andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 `StrongNameSignatureVerificationEx`bietet eine ähnliche Funktion wie die [StrongNameSignatureVerification](strongnamesignatureverification-function.md) -Funktion. Der zweite Eingabeparameter und der Output-Parameter für `StrongNameSignatureVerificationEx` sind jedoch vom Typ `BOOLEAN` anstelle von. `DWORD`  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerificationEx-Methode](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification-Methode](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
