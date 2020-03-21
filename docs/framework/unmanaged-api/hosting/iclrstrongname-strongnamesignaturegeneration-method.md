---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178052"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration-Methode
Generiert eine Signatur mit starkem Namen für die angegebene Assembly.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die die Signatur mit starkem Namen generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` null `wszKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden. In diesem Fall wird das im Container gespeicherte Schlüsselpaar zum Signieren der Datei verwendet.  
  
 Wenn `pbKeyBlob` es nicht null ist, wird davon ausgegangen, dass das Schlüsselpaar im PpbLOB (Key Binary Large Object) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Derzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentliche/private Schlüsselpaar. Dieses Paar hat das Format, das `CryptExportKey` von der Win32-Funktion erstellt wurde. Wenn `pbKeyBlob` null ist, wird `wszKeyContainer` davon ausgegangen, dass der von festgelegte Schlüsselcontainer das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe von in `pbKeyBlob`Bytes von .  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an den die Common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` null, speichert die Laufzeit die Signatur `wszFilePath`in der datei, die von angegeben wird.  
  
 Wenn `ppbSignatureBlob` dies nicht null ist, weist die Common Language Runtime Speicherplatz zu, in dem die Signatur zurückgegeben werden soll. Der Aufrufer muss diesen Speicherplatz mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) freizugeben.  
  
 `pcbSignatureBlob`  
 [out] Die Größe der zurückgegebenen Signatur in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Bemerkungen  
 Geben Sie `wszFilePath` NULL an, um die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureGenerationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
