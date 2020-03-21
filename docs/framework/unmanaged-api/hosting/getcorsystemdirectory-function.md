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
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178203"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory-Funktion
Gibt das Installationsverzeichnis der Common Language Runtime (CLR) zurück, die in den Prozess geladen wird. Das Installationsverzeichnis ist voll qualifiziert, z. B. "c:'windows'microsoft.net'framework'v1.0.3705'.  
  
 Diese Funktion ist als veraltet markiert. Sie wird durch die [ICLRRuntimeInfo::GetRuntimeDirectory-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) ersetzt, die in .NET Framework 4 bereitgestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parameter  
 `pbuffer`  
 [out] Ein Puffer, in dem die Laufzeit eine Zeichenfolge zurückgibt, die den vollqualifizierten Namen des Installationsverzeichnisses für die Laufzeit enthält, die in den Prozess geladen wird. Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der auf dem Computer installierten Laufzeit zurück.  
  
 `cchBuffer`  
 [in] Die Größe von in `pbuffer`Bytes von .  
  
 `dwLength`  
 [out] Die Anzahl der `pbuffer`in zurückgegebenen Zeichen.  
  
## <a name="remarks"></a>Bemerkungen  
  
> [!CAUTION]
> Verwenden Sie diese Funktion nicht in Prozessen, in denen Version 4 der CLR ausgeführt wird. Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für diese Version zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
