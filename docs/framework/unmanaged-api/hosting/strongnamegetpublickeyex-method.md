---
title: StrongNameGetPublicKeyEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 834292192aa447a113372bc8807041954b39a115
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937772"
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx-Methode
Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab und gibt einen Hash Algorithmus und einen Signatur Algorithmus an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pwzKeyContainer`  
 in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält. Wenn `pbKeyBlob` NULL ist, muss `szKeyContainer` einen gültigen Container innerhalb des Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) angeben. In diesem Fall extrahiert die `StrongNameGetPublicKeyEx`-Methode den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.  
  
 Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein. Zurzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel. Dieses Paar weist das Format auf, das von der Win32-`CryptExportKey`-Funktion erstellt wird. Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der von `szKeyContainer` angegebene Schlüssel Container das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 in Die Größe `pbKeyBlob`in Byte.  
  
 `ppbPublicKeyBlob`  
 vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel. Der `ppbPublicKeyBlob`-Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben. Der Aufrufer muss den Speicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.  
  
 `pcbPublicKeyBlob`  
 vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.  
  
 `uHashAlgId`  
 in Der Assembly-Hash Algorithmus. Eine Liste der akzeptierten Werte finden Sie im Abschnitt "Hinweise".  
  
 `uReserved`  
 in Für zukünftige Verwendung reserviert. der Standardwert ist NULL.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) -Struktur enthalten.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle wird der Satz akzeptierter Werte für den `uHashAlgId`-Parameter angezeigt.  
  
|-Name|{2&gt;Wert&lt;2}|  
|----------|-----------|  
|Keine|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameTokenFromPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
