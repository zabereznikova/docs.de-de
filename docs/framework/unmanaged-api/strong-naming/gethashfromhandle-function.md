---
title: GetHashFromHandle-Funktion
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa5d5ee469d41cca46ea05fa4111ce3abff808d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771904"
---
# <a name="gethashfromhandle-function"></a>GetHashFromHandle-Funktion
Generiert einen Hashwert für den Inhalt der Datei mit dem angegebenen Dateihandle unter Verwendung des angegebenen Hashalgorithmus.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hFile`  
 [in] Das Handle der Datei, der Hashwert berechnet werden soll.  
  
 `piHashAlg`  
 [in, out] Eine Konstante, die den Hashalgorithmus angibt. Verwenden Sie 0 (null), für den Standardalgorithmus.  
  
 `pbHash`  
 [out] Der zurückgegebene Hashpuffer.  
  
 `cchHash`  
 [in] Die angeforderte maximale Größe des `pbHash`.  
  
 `pchHash`  
 [out] Die Größe in Bytes, des zurückgegebenen `pbHash`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetHashFromHandle-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
