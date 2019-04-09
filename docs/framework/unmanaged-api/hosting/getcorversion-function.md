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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f66e00c3334aecdf8c653f57e28d1b327c4170e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094052"
---
# <a name="getcorversion-function"></a>GetCORVersion-Funktion
Gibt die Versionsnummer der die common Language Runtime (CLR), die im aktuellen Prozess ausgeführt wird.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parameter  
 `pbuffer`  
 Ein Zeiger auf einen Puffer, in dem die CLR zurückgegeben wird eine Zeichenfolge, die Angabe der Version der Laufzeit, die derzeit in den Prozess geladen wird. Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), z. B. "v1.0.1216". Wenn die Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.  
  
 `cchBuffer`  
 Die Anzahl der Zeichen (`WCHAR`s), die gespeichert werden können, im `pbuffer`.  
  
 `dwLength`  
 Ein Zeiger auf die Anzahl der Zeichen im tatsächlich zurückgegebenen `pbuffer`. Wenn `pbuffer` ist ein null-Zeiger der Common Language Runtime gibt E_POINTER zurück. Wenn die Anzahl der Zeichen größer ist. Klicken Sie dann die Länge des `pbuffer` , gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
