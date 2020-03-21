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
ms.openlocfilehash: 9db583c7064cb910b29e84437f31143dac0d3ec9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175082"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW-Funktion
Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::GetHashFromFileW-Methode.](../hosting/iclrstrongname-gethashfromfilew-method.md)  
  
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
 [in] Der Unicode-Name der zu hashenden Datei.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus, der beim Generieren des Hashs verwendet werden soll. Gültige Algorithmen sind die, die von der Win32 CryptoAPI definiert werden. Wenn `piHashAlg` auf 0 gesetzt ist, wird der Standardalgorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 [out] Ein Bytearray, das den generierten Hash enthält.  
  
 `cchHash`  
 [in] Die maximale Größe des Puffers, auf die von `pbHash`verwiesen wird.  
  
 `pchHash`  
 [out] Die Größe von in `pbHash`Bytes von .  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Funktion ist die gleiche wie [GetHashFromFile](gethashfromfile-function.md), mit der Ausnahme, dass die Dateinamenspezifikation Unicode anstelle von ANSI ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetHashFromFileW-Methode](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile-Methode](../hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
