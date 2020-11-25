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
ms.openlocfilehash: f28ee5767997240018d182b8303e4f65be81c702
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708542"
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx-Funktion

Generiert ein neues öffentliches/privates Schlüsselpaar mit der angegebenen Schlüsselgröße für eine starke namens Verwendung.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) -Methode.  
  
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
 in Der angeforderte Schlüssel Container Name. `wszKeyContainer` muss eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 in Gibt an, ob der Schlüssel registriert bleiben soll. Die folgenden Werte werden unterstützt:  
  
- 0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.  
  
 `dwKeySize`  
 in Die angeforderte Größe des Schlüssels in Bits.  
  
 `ppbKeyBlob`  
 vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.  
  
 `pcbKeyBlob`  
 vorgenommen Die Größe von in Bytes `ppbKeyBlob` .  
  
## <a name="return-value"></a>Rückgabewert  

 `true` nach erfolgreichem Abschluss: andernfalls `false` .  
  
## <a name="remarks"></a>Hinweise  

 Die .NET Framework Versionen 1,0 und 1,1 erfordern eine `dwKeySize` von 1024 Bits zum Signieren einer Assembly mit einem starken Namen; Version 2,0 fügt Unterstützung für 2048-Bit-Schlüssel hinzu.  
  
 Nachdem der Schlüssel abgerufen wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers abrufen.  
  
 Wenn die `StrongNameKeyGenEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameKeyGenEx-Methode](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [StrongNameKeyGen-Methode](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
