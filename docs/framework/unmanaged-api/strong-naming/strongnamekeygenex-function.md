---
title: StrongNameKeyGenEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2ed9ba4b580b8f64fc05dbb429742442a36acf5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757467"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx-Funktion
Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für die Verwendung der starken Namen an.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszKeyContainer`  
 [in] Der angeforderte Schlüsselcontainer-Name. `wszKeyContainer` muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 [in] Gibt an, ob den Schlüssel registriert bleiben soll. Die folgenden Werte werden unterstützt:  
  
- 0 x 00000000 - wird verwendet, wenn `wszKeyContainer` null ist, um einen temporären Schlüsselcontainernamen zu generieren.  
  
- 0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.  
  
 `dwKeySize`  
 [in] Die angeforderte Größe des Schlüssels in Bits.  
  
 `ppbKeyBlob`  
 [out] Das zurückgegebene öffentliches/privates Schlüsselpaar.  
  
 `pcbKeyBlob`  
 [out] Die Größe in Bytes, des `ppbKeyBlob`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die .NET Framework-Versionen 1.0 und 1.1 erfordert eine `dwKeySize` von 1024 Bit zum Signieren einer Assembly mit einem starken Namen, Version 2.0 bietet 2048-Bit-Schlüssel unterstützt.  
  
 Nachdem der Schlüssel abgerufen werden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.  
  
 Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameKeyGenEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
