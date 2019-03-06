---
title: GetHashFromAssemblyFile-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09fb98c5524446041e0e7a9484322f835b9d9801
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474461"
---
# <a name="gethashfromassemblyfile-function"></a>GetHashFromAssemblyFile-Funktion
Ruft einen Hash der angegebenen Assemblydatei unter Verwendung des angegebenen Hashalgorithmus ab.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szFilePath`  
 [in] Der Pfad zu der Datei, der Hashwert berechnet werden soll.  
  
 `piHashAlg`  
 [in, out] Eine Konstante, die den Hashalgorithmus angibt. Verwenden Sie 0 (null), für den Standard-Hashalgorithmus.  
  
 `pbHash`  
 [out] Der zurückgegebene Hashpuffer.  
  
 `cchHash`  
 [in] Die angeforderte maximale Größe des `pbHash`.  
  
 `pchHash`  
 [out] Die zurückgegebene Größe in Bytes, `pbHash`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [GetHashFromAssemblyFile-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [GetHashFromAssemblyFileW-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
