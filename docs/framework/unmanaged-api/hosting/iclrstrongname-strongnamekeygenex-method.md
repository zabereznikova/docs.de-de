---
title: ICLRStrongName::StrongNameKeyGenEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGenEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 581f486a2def90f44c0fb3f1bcf9d3bbcc1fc317
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>ICLRStrongName::StrongNameKeyGenEx-Methode
Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszKeyContainer`  
 [in] Der angeforderte Schlüsselcontainer-Name. `wszKeyContainer`muss entweder eine leere Zeichenfolge oder Null, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 [in] Ein Wert, der angibt, ob der Schlüssel verlassen registriert. Die folgenden Werte werden unterstützt:  
  
-   0 x 00000000 – wird verwendet, wenn `wszKeyContainer` ist null, um einen temporären Schlüsselcontainernamen zu generieren.  
  
-   0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.  
  
 `dwKeySize`  
 [in] Die angeforderte Größe des Schlüssels in Bits.  
  
 `ppbKeyBlob`  
 [out] Das zurückgegebene öffentlichen/privaten Schlüsselpaar.  
  
 `pcbKeyBlob`  
 [out] Die Größe in Bytes, der `ppbKeyBlob`.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Die .NET Framework-Versionen 1.0 und 1.1 erfordern eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 fügt 2048-Bit-Schlüssel unterstützt.  
  
 Nachdem der Schlüssel abgerufen wurden, sollten Sie Aufrufen der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode, um den belegten Speicher freizugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameKeyGen-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
