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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799264"
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
 in Die angeforderte maximale Größe `pbHash`von.  
  
 `pchHash`  
 vorgenommen Die zurückgegebene Größe von `pbHash`in Bytes.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetHashFromAssemblyFileW-Methode](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [GetHashFromAssemblyFile-Methode](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
