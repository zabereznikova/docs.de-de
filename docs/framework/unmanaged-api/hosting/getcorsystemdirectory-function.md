---
title: GetCORSystemDirectory-Funktion
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008514e3637a980f3722d0c9896a17be33d54c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory-Funktion
Gibt das Installationsverzeichnis der common Language Runtime (CLR), die in den Prozess geladen wird. Das Installationsverzeichnis ist vollqualifizierte, z. B. "c:\windows\microsoft.net\framework\v1.0.3705".  
  
 Diese Funktion ist veraltet. Er ersetzt wird, durch die [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) Methode bereitgestellt wird, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `pbuffer`  
 [out] Ein Puffer, in dem die Common Language Runtime eine Zeichenfolge zurückgibt, die für die Laufzeit der vollqualifizierte Name des Installationsverzeichnisses enthält, die in den Prozess geladen wird. Wenn die Common Language Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.  
  
 `cchBuffer`  
 [in] Die Größe in Bytes, der `pbuffer`.  
  
 `dwLength`  
 [out] Die Anzahl der Zeichen im zurückgegebenen `pbuffer`.  
  
## <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Verwenden Sie diese Funktion nicht in Version 4 der CLR ausgeführten Prozessen. Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für die jeweilige Version.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
