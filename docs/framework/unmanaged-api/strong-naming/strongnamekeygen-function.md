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
ms.openlocfilehash: 4844701784a3e6a1008a5deb2bdff3b3ba47aa7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691408"
---
# <a name="strongnamekeygen-function"></a>StrongNameKeyGen-Funktion

Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszKeyContainer`  
 in Der angeforderte Schlüssel Container Name. `wszKeyContainer` muss eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 in Gibt an, ob der Schlüssel registriert bleiben soll. Die folgenden Werte werden unterstützt:  
  
- 0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.  
  
 `ppbKeyBlob`  
 vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.  
  
 `pcbKeyBlob`  
 vorgenommen Die Größe von in Bytes `ppbKeyBlob` .  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Die `StrongNameKeyGen` -Funktion erstellt einen 1024-Bit-Schlüssel. Nachdem der Schlüssel abgerufen wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers abrufen.  
  
 Wenn die `StrongNameKeyGen` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameKeyGen-Methode](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [StrongNameKeyGenEx-Methode](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
