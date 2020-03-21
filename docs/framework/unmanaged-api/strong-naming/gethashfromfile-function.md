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
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176980"
---
# <a name="gethashfromfile-function"></a>GetHashFromFile-Funktion
Generiert einen Hashwert für den Inhalt der angegebenen Datei.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName::GetHashFromFile-Methode.](../hosting/iclrstrongname-gethashfromfile-method.md)  
  
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
 [in] Der Name der zu hashenden Datei.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus, der beim Generieren des Hashs verwendet werden soll. Gültige Algorithmen sind die, die von der Win32 CryptoAPI definiert werden. Wenn `piHashAlg` auf 0 gesetzt ist, wird der Standardalgorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 [out] Ein Bytearray, das den generierten Hash enthält.  
  
 `cchHash`  
 [in] Die maximale Größe des `pbHash` Puffers, auf den verweist.  
  
 `pchHash`  
 [out] Die Größe der zurückgegebenen `pbHash`in Bytes .  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Funktion ist die gleiche wie [GetHashFromFileW](gethashfromfilew-function.md), mit der Ausnahme, dass die Dateinamenspezifikation ANSI anstelle von Unicode ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetHashFromFile-Methode](../hosting/iclrstrongname-gethashfromfile-method.md)
- [GetHashFromFileW-Methode](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
