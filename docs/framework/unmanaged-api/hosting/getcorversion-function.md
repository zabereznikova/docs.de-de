---
title: GetCORVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1283abaf6b08af1d842d8fe4469f7f6c15e38ec5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136422"
---
# <a name="getcorversion-function"></a>GetCORVersion-Funktion
Gibt die Versionsnummer der Common Language Runtime (CLR) zurück, die im aktuellen Prozess ausgeführt wird.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parameter  
 `pbuffer`  
 Ein Zeiger auf einen Puffer, in dem die CLR eine Zeichenfolge zurückgibt, die die Version der Laufzeit angibt, die gerade in den Prozess geladen wird. Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichen folgen, die an [corbindtoriuntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)übermittelt werden, z. b. "v 1.0.1216". Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die aktuelle Version der Laufzeit zurück, die auf dem Computer installiert ist.  
  
 `cchBuffer`  
 Die Anzahl der Zeichen (`WCHAR`en), die in `pbuffer`aufbewahrt werden können.  
  
 `dwLength`  
 Ein Zeiger auf die Anzahl der Zeichen, die tatsächlich in `pbuffer`zurückgegeben werden. Wenn `pbuffer` ein NULL-Zeiger ist, gibt die Laufzeit E_POINTER zurück. Wenn die Anzahl der Zeichen größer ist als die Länge der `pbuffer`, gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
