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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be512bab30e08ddeb7deadf8a29263e928549a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000375"
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW-Funktion
Generiert einen Hashwert für den Inhalt der durch eine Unicode-Zeichenfolge angegebenen Datei.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Der Unicode-Name der Datei für den Hash.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus beim Generieren des Hashs verwendet werden soll. Gültige Algorithmen sind durch Win32 Crypto-API definiert. Wenn `piHashAlg` ist auf 0 festgelegt, den Standardalgorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 [out] Ein Bytearray, die den generierten Hash enthält.  
  
 `cchHash`  
 [in] Die maximale Größe des Puffers verweist `pbHash`.  
  
 `pchHash`  
 [out] Die Größe in Bytes, des `pbHash`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist identisch mit [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), außer dass der Dateiname Unicode anstelle von ANSI codiert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetHashFromFileW-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [GetHashFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
