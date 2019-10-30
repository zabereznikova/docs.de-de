---
title: GetHashFromFileW-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
ms.openlocfilehash: db6f39119d143d27c0d3a80a9c65565d4dfd0d39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140675"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW-Funktion
Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 in Der Unicode-Name der zu hashenden Datei.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus, der beim Erzeugen des Hashwerts verwendet werden soll. Gültige Algorithmen sind die, die von der Win32-CryptoAPI definiert werden. Wenn `piHashAlg` auf 0 festgelegt ist, wird der Standard Algorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 vorgenommen Ein Bytearray, das den generierten Hash enthält.  
  
 `cchHash`  
 in Die maximale Größe des Puffers, auf den `pbHash`zeigt.  
  
 `pchHash`  
 vorgenommen Die Größe `pbHash`in Byte.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist mit [GetHashFromFile](gethashfromfile-function.md)identisch, mit der Ausnahme, dass die Dateinamen Spezifikation anstelle von ANSI Unicode ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetHashFromFileW-Methode](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile-Methode](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
