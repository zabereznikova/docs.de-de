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
ms.openlocfilehash: 5a20bde64830617090c92afe5fae3a603cf9103b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763128"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey-Methode
Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab. Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.  
  
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
 in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält. Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des CSP angeben. In diesem Fall extrahiert die [ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) -Methode den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.  
  
 Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein. Zurzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel. Dieses Paar weist das Format auf, das von der Win32-Funktion erstellt wird `CryptExportKey` . Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von angegebene Schlüssel Container `szKeyContainer` das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 in Die Größe von in Bytes `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel. Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben. Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.  
  
 `pcbPublicKeyBlob`  
 vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) -Struktur enthalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameTokenFromPublicKey-Methode](iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob-Struktur](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
