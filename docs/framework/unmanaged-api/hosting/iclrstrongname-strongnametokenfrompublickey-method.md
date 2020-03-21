---
title: ICLRStrongName::StrongNameTokenFromPublicKey-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176317"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey-Methode
Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt. Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbPublicKeyBlob`  
 [in] Eine Struktur vom Typ [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.  
  
 `cbPublicKeyBlob`  
 [in] Die Größe von in `pbPublicKeyBlob`Bytes von .  
  
 `ppbStrongNameToken`  
 [out] Das Token mit starkem Namen, das dem in `pbPublicKeyBlob`übergebenen Schlüssel entspricht. Die Common Language Runtime weist den Speicher zu, in dem das Token zurückgegeben werden soll. Der Aufrufer muss diesen Speicher mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) freizugeben.  
  
 `pcbStrongNameToken`  
 [out] Die Größe des zurückgegebenen Tokens für starken Namen in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, der zum Speichern von Schlüsselinformationen in Metadaten verwendet wird. Insbesondere werden Token mit starkem Namen in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
