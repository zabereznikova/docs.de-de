---
title: StrongNameKeyGen-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0cb64653df7b59703ef87610bcc686a66205e8b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485227"
---
# <a name="strongnamekeygen-function"></a>StrongNameKeyGen-Funktion
Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszKeyContainer`  
 [in] Der angeforderte Schlüsselcontainer-Name. `wszKeyContainer` muss eine nicht leere Zeichenfolge sein, oder null, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 [in] Gibt an, ob den Schlüssel registriert bleiben soll. Die folgenden Werte werden unterstützt:  
  
-   0 x 00000000 - wird verwendet, wenn `wszKeyContainer` null ist, um einen temporären Schlüsselcontainernamen zu generieren.  
  
-   0 x 00000001 (`SN_LEAVE_KEY`) – gibt an, dass der Schlüssel registriert werden soll.  
  
 `ppbKeyBlob`  
 [out] Das zurückgegebene öffentliches/privates Schlüsselpaar.  
  
 `pcbKeyBlob`  
 [out] Die Größe in Bytes, des `ppbKeyBlob`.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Die `StrongNameKeyGen` Funktion wird ein 1024-Bit-Schlüssel erstellt. Nachdem der Schlüssel abgerufen werden, sollten Sie Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.  
  
 Wenn die `StrongNameKeyGen` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [StrongNameKeyGen-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [StrongNameKeyGenEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
