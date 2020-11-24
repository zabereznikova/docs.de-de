---
title: ICLRStrongName::StrongNameKeyGen-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
ms.openlocfilehash: 42a9fc1a05e97bbd893f0a2e77087e6524ad844f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674540"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>ICLRStrongName::StrongNameKeyGen-Methode

Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszKeyContainer`  
 in Der angeforderte Schlüssel Container Name. `wszKeyContainer` muss entweder eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.  
  
 `dwFlags`  
 in Ein-Wert, der angibt, ob der Schlüssel registriert bleiben soll. Die folgenden Werte werden unterstützt:  
  
- 0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.  
  
- 0x00000001 ( `SN_LEAVE_KEY` ): gibt an, dass der Schlüssel registriert bleiben soll.  
  
 `ppbKeyBlob`  
 vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.  
  
 `pcbKeyBlob`  
 vorgenommen Die Größe von in Bytes `ppbKeyBlob` .  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="remarks"></a>Hinweise  

 Die [ICLRStrongName:: StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md) -Methode erstellt einen 1024-Bit-Schlüssel. Nachdem der Schlüssel abgerufen wurde, sollten Sie die [ICLRStrongName:: strongnamefrebuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode abrufen, um den zugewiesenen Speicher freizugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameKeyGenEx-Methode](iclrstrongname-strongnamekeygenex-method.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
