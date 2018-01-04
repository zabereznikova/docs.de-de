---
title: GetHashFromFileW-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFileW
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFileW
helpviewer_keywords: GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7d62526a6ac9bb06a7de8287c9687933402bfb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromfilew-function"></a>GetHashFromFileW-Funktion
Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben.  
  
 Diese Funktion ist veraltet. Verwenden der [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) Methode stattdessen.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Unicode-Name der Datei für den Hash.  
  
 `piHashAlg`  
 [in, out] Der Algorithmus beim Generieren des Hashs verwendet wird. Gültige Algorithmen sind diejenigen, die von Win32 Crypto-API definiert. Wenn `piHashAlg` ist auf 0 festgelegt, der Standardalgorithmus CALG_SHA-1 verwendet.  
  
 `pbHash`  
 [out] Ein Bytearray, das den generierten Hash enthält.  
  
 `cchHash`  
 [in] Die maximale Größe des Puffers verweist `pbHash`.  
  
 `pchHash`  
 [out] Die Größe in Bytes, der `pbHash`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion ist identisch mit [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), außer dass die Namen Dateispezifikation Unicode anstelle von ANSI codiert ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [GetHashFromFileW-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [GetHashFromFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
