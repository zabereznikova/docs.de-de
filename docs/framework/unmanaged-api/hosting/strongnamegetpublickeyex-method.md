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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176226"
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx-Methode
Ruft den öffentlichen Schlüssel von einem öffentlichen/privaten Schlüsselpaar ab und gibt einen Hashalgorithmus und einen Signaturalgorithmus an.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pwzKeyContainer`  
 [in] Der Name des Schlüsselcontainers, der das öffentliche/private Schlüsselpaar enthält. Wenn `pbKeyBlob` null `szKeyContainer` ist, muss ein gültiger Container innerhalb des Kryptografiedienstanbieters (Cryptographic Service Provider, CSP) angegeben werden. In diesem Fall `StrongNameGetPublicKeyEx` extrahiert die Methode den öffentlichen Schlüssel aus dem im Container gespeicherten Schlüsselpaar.  
  
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
  
 `uHashAlgId`  
 [in] Der Assemblyhashalgorithmus. Eine Liste der akzeptierten Werte finden Sie im Abschnitt "Bemerkungen".  
  
 `uReserved`  
 [in] Reserviert für die zukünftige Verwendung; Standardwert auf null.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Bemerkungen  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) enthalten.  
  
## <a name="remarks"></a>Bemerkungen  
 Die folgende Tabelle zeigt den Satz `uHashAlgId` der akzeptierten Werte für den Parameter.  
  
|Name|value|  
|----------|-----------|  
|Keine|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameTokenFromPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [PublicKeyBlob-Struktur](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [StrongNameGetPublicKey-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
