---
title: StrongNameGetPublicKey-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176928"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey-Funktion
Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab. Das Schlüsselpaar kann entweder als Schlüsselcontainername innerhalb eines Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) oder als unformatierte Auflistung von Bytes angegeben werden.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::StrongNameGetPublicKey-Methode.](../hosting/iclrstrongname-strongnamegetpublickey-method.md)  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szKeyContainer`  
 [in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält. Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des CSP angegeben werden. `StrongNameGetPublicKey` In diesem Fall wird der öffentliche Schlüssel aus dem im Container gespeicherten Schlüsselpaar extrahiert.  
  
 Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Derzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentliche/private Schlüsselpaar. Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde. Wenn `pbKeyBlob` null ist, wird `szKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe von in `pbKeyBlob`Bytes von .  
  
 `ppbPublicKeyBlob`  
 [out] Der zurückgegebene BLOB des öffentlichen Schlüssels. Der `ppbPublicKeyBlob` Parameter wird von der Common Language Runtime zugewiesen und an den Aufrufer zurückgegeben. Der Aufrufer muss den Speicher mithilfe der [StrongNameFreeBuffer-Funktion](strongnamefreebuffer-function.md) freimachen.  
  
 `pcbPublicKeyBlob`  
 [out] Die Größe des zurückgegebenen bLOB für den öffentlichen Schlüssel.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Bemerkungen  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](publickeyblob-structure.md) enthalten.  
  
 Wenn `StrongNameGetPublicKey` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetPublicKey-Methode](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey-Methode](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob-Struktur](publickeyblob-structure.md)
