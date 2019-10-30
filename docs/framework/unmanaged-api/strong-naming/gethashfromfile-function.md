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
ms.openlocfilehash: ffa25b1ec6fda80099f333c1d0a4cf57b76379e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140690"
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
 in Die maximale Puffergröße, auf die `pbHash` zeigt.  
  
 `pchHash`  
 vorgenommen Die Größe (in Bytes) des zurückgegebenen `pbHash`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist mit [GetHashFromFileW](gethashfromfilew-function.md)identisch, mit der Ausnahme, dass die Dateinamen Spezifikation ANSI anstelle von Unicode ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetHashFromFile-Methode](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW-Methode](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
