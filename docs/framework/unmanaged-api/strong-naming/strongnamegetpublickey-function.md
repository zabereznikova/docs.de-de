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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae87ebd0b8225f14ca029fac80528d47f5a866cf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799058"
---
# <a name="strongnamegetpublickey-function"></a>StrongNameGetPublicKey-Funktion
Ruft den öffentlichen Schlüssel aus einem privaten/öffentlichen Schlüsselpaar ab. Das Schlüsselpaar kann entweder als Schlüssel Container Name innerhalb eines Kryptografiedienstanbieters (kryptografischen Service Provider, CSP) oder als unformatierte Sammlung von Bytes angegeben werden.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) -Methode.  
  
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
 in Der Name des Schlüssel Containers, der das Paar aus öffentlichem und privatem Schlüssel enthält. Wenn `pbKeyBlob` NULL ist, `szKeyContainer` muss einen gültigen Container innerhalb des CSP angeben. In diesem Fall extrahiert `StrongNameGetPublicKey` den öffentlichen Schlüssel aus dem Schlüsselpaar, das im Container gespeichert ist.  
  
 Wenn `pbKeyBlob` nicht NULL ist, wird angenommen, dass das Schlüsselpaar im Schlüssel Binary Large Object (BLOB) enthalten ist.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA)-Signatur Schlüssel sein. Zurzeit werden keine anderen Schlüsseltypen unterstützt.  
  
 `pbKeyBlob`  
 in Ein Zeiger auf das Paar aus öffentlichem und privatem Schlüssel. Dieses Paar weist das Format auf, das von der `CryptExportKey` Win32-Funktion erstellt wird. Wenn `pbKeyBlob` NULL ist, wird angenommen, dass der `szKeyContainer` von angegebene Schlüssel Container das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 in Die Größe von `pbKeyBlob`in Bytes.  
  
 `ppbPublicKeyBlob`  
 vorgenommen Das zurückgegebene BLOB für öffentliche Schlüssel. Der `ppbPublicKeyBlob` -Parameter wird vom Common Language Runtime zugeordnet und an den Aufrufer zurückgegeben. Der Aufrufer muss den Speicher mithilfe der [StrongNameFreeBuffer](strongnamefreebuffer-function.md) -Funktion freigeben.  
  
 `pcbPublicKeyBlob`  
 vorgenommen Die Größe des zurückgegebenen BLOBs für öffentliche Schlüssel.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`nach erfolgreichem Abschluss: `false`andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Der öffentliche Schlüssel ist in einer [PublicKeyBlob](publickeyblob-structure.md) -Struktur enthalten.  
  
 Wenn die `StrongNameGetPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameGetPublicKey-Methode](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [StrongNameTokenFromPublicKey-Methode](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
- [PublicKeyBlob-Struktur](publickeyblob-structure.md)
