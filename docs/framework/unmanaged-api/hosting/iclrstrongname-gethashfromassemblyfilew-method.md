---
title: ICLRStrongName::GetHashFromAssemblyFileW-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b10d74cd54afc3c93578710d4a2e339a1f8761f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a>ICLRStrongName::GetHashFromAssemblyFileW-Methode
Generiert einen Hash des Inhalts der Datei durch eine Unicode-Zeichenfolge angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zu der Datei, der Hashwert berechnet werden soll. Dieser Parameter muss eine Unicode-Zeichenfolge sein.  
  
 `piHashAlg`  
 [in, out] Eine Konstante, die den Hashalgorithmus angibt. Verwenden Sie 0 (null), für die Standard-Hash-Algorithmus.  
  
 `pbHash`  
 [out] Der zurückgegebene Hashpuffer.  
  
 `cchHash`  
 [in] Die angeforderte maximale Größe der `pbHash`.  
  
 `pchHash`  
 [out] Die Größe in Bytes, der zurückgegebenen `pbHash`.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [GetHashFromAssemblyFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
