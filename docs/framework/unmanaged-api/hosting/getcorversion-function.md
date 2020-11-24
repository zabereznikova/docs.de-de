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
ms.openlocfilehash: e7ef3f300c8cfa0c275d15913e171abe09385eea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681209"
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
 Ein Zeiger auf einen Puffer, in dem die CLR eine Zeichenfolge zurückgibt, die die Version der Laufzeit angibt, die gerade in den Prozess geladen wird. Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichen folgen, die an [corbindtoriuntimeex](corbindtoruntimeex-function.md)übermittelt werden, z. b. "v 1.0.1216". Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die aktuelle Version der Laufzeit zurück, die auf dem Computer installiert ist.  
  
 `cchBuffer`  
 Die Anzahl der Zeichen `WCHAR` , die in aufbewahrt werden können `pbuffer` .  
  
 `dwLength`  
 Ein Zeiger auf die Anzahl von Zeichen, die tatsächlich in zurückgegeben werden `pbuffer` . Wenn `pbuffer` ein NULL-Zeiger ist, gibt die Laufzeit E_POINTER zurück. Wenn die Anzahl der Zeichen größer als die Länge von ist `pbuffer` , gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
