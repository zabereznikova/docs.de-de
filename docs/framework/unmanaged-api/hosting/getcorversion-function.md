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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178193"
---
# <a name="getcorversion-function"></a>GetCORVersion-Funktion
Gibt die Versionsnummer der Common Language Runtime (CLR) zurück, die im aktuellen Prozess ausgeführt wird.  
  
 Diese Funktion ist in .NET Framework 4 veraltet.  
  
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
 Ein Zeiger auf einen Puffer, in dem die CLR eine Zeichenfolge zurückgibt, die die Version der Laufzeit angibt, die derzeit in den Prozess geladen wird. Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)übergeben werden, z. B. "v1.0.1216". Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der auf dem Computer installierten Laufzeit zurück.  
  
 `cchBuffer`  
 Die Anzahl der`WCHAR`Zeichen (s), `pbuffer`die in gehalten werden können.  
  
 `dwLength`  
 Ein Zeiger auf die Anzahl der `pbuffer`tatsächlich zurückgegebenen Zeichen in . Wenn `pbuffer` es sich um einen Nullzeiger handelt, gibt die Laufzeit E_POINTER zurück. Wenn die Anzahl der Zeichen größer `pbuffer` ist als die Länge von, gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
