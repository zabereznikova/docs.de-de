---
title: GetHashFromAssemblyFileW-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: b895c77850c0457fd2a152c1128c016093599f76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730980"
---
# <a name="gethashfromassemblyfilew-function"></a>GetHashFromAssemblyFileW-Funktion

Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab. Der Pfad zur Assemblydatei muss als Unicode-Zeichenfolge angegeben werden.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `wszFilePath`  
 in Der Pfad zu der Datei, für die der Hashwert verwendet werden soll. Dieser Parameter muss eine Unicode-Zeichenfolge sein.  
  
 `piHashAlg`  
 [in, out] Eine-Konstante, die den Hash Algorithmus angibt. Verwenden Sie 0 für den Standard Hash Algorithmus.  
  
 `pbHash`  
 vorgenommen Der zurückgegebene Hash Puffer.  
  
 `cchHash`  
 in Die angeforderte maximale Größe von `pbHash` .  
  
 `pchHash`  
 vorgenommen Die zurückgegebene Größe von in Bytes `pbHash` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetHashFromAssemblyFileW-Methode](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [GetHashFromAssemblyFile-Methode](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
