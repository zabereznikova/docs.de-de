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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e595904eacebdd42467fc4e0550db77578c075c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169727"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey-Methode
Ruft ein Token, das einen öffentlichen Schlüssel darstellt. Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbPublicKeyBlob`  
 [in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.  
  
 `cbPublicKeyBlob`  
 [in] Die Größe in Bytes, des `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 [out] Entspricht dem Schlüssel Token mit starkem Namen übergegebenen `pbPublicKeyBlob`. Die common Language Runtime ordnet den Speicher in den das Token zurückgegeben werden sollen. Der Aufrufer muss diesen Arbeitsspeicher freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbStrongNameToken`  
 [out] Die Größe in Bytes, der das zurückgegebene strong Name-Token.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel, der verwendet wird, um Platz zu sparen, wenn wichtige Informationen in den Metadaten gespeichert. Insbesondere werden Token mit starkem Namen in Assemblyverweise verwendet, um auf die abhängige Assembly zu verweisen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
