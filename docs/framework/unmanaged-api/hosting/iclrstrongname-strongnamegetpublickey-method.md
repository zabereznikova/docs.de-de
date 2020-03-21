---
title: ICLRStrongName::StrongNameGetPublicKey-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181934"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey-Methode
Ruft den öffentlichen Schlüssel von einem öffentlichen/privaten Schlüsselpaar ab. Das Schlüsselpaar kann entweder als Schlüsselcontainername innerhalb eines Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) oder als unformatierte Auflistung von Bytes angegeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szKeyContainer`  
 [in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält. Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des CSP angegeben werden. In diesem Fall extrahiert die [ICLRStrongName::StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) den öffentlichen Schlüssel aus dem im Container gespeicherten Schlüsselpaar.  
  
 Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Derzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentliche/private Schlüsselpaar. Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde. Wenn `pbKeyBlob` null ist, wird `szKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe von in `pbKeyBlob`Bytes von .  
  
 `ppbPublicKeyBlob`  
 [out] Der zurückgegebene BLOB des öffentlichen Schlüssels. Der `ppbPublicKeyBlob` Parameter wird von der Common Language Runtime zugewiesen und an den Aufrufer zurückgegeben. Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode freigeben.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
  
 `pcbPublicKeyBlob`  
 [out] Die Größe des zurückgegebenen bLOB für den öffentlichen Schlüssel.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Bemerkungen  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) enthalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameTokenFromPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
