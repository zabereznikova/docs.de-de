---
title: GetHashFromFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ee9f9cd9a9f35c6c54497ad382bb6f9817d186bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732371"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile-Funktion

Generiert einen Hashwert für den Inhalt der angegebenen Datei.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szFilePath`  
 in Der Name der zu hashenden Datei.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll. Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden. Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 vorgenommen Ein Bytearray, das den generierten Hash enthält.  
  
 `cchHash`  
 in Die maximale Größe des Puffers, `pbHash` auf den verweist.  
  
 `pchHash`  
 vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash` .  
  
## <a name="remarks"></a>Hinweise  

 Diese Funktion ist mit [GetHashFromFileW](gethashfromfilew-function.md)identisch, mit der Ausnahme, dass die Dateinamen Spezifikation ANSI anstelle von Unicode ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetHashFromFile-Methode](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW-Methode](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
