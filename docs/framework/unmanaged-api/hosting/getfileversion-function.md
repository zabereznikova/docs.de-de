---
title: GetFileVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f5508e9ee41d8670b43d5b219846237e11fc8f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778145"
---
# <a name="getfileversion-function"></a>GetFileVersion-Funktion
Ruft die common Language Runtime (CLR) Versionsinformationen von der angegebenen Datei, die mithilfe des angegebenen Puffers ab.  
  
 Diese Funktion ist in .NET Framework 4 veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szFilename`  
 [in] Der Pfad der Datei, die untersucht werden.  
  
 `szBuffer`  
 [in, out] Der Puffer zugeordnet werden, für die Versionsinformationen, die zurückgegeben wird.  
  
 `cchBuffer`  
 [in] Die Größe in Breitzeichen, der `szBuffer`.  
  
 `dwLength`  
 [out] Die Größe in Bytes, des zurückgegebenen `szBuffer`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
