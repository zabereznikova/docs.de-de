---
title: ICLRStrongName::GetHashFromHandle-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
ms.openlocfilehash: 68bfdb2f66147b54c75b8f577a01278016e248b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685733"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a>ICLRStrongName::GetHashFromHandle-Methode

Generiert einen Hash über den Inhalt der Datei mit dem angegebenen Datei Handle unter Verwendung des angegebenen Hash Algorithmus.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `hFile`  
 in Das Handle der Datei, für die der Hashwert verwendet werden soll.  
  
 `piHashAlg`  
 [in, out] Eine-Konstante, die den Hash Algorithmus angibt. Verwenden Sie 0 (null) für den Standard Algorithmus.  
  
 `pbHash`  
 vorgenommen Der zurückgegebene Hash Puffer.  
  
 `cchHash`  
 in Die angeforderte maximale Größe von `pbHash` .  
  
 `pchHash`  
 vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
