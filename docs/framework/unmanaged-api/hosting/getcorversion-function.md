---
title: GetCORVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c61dd0b10bc0229d8f0d7dd4f6357ddaf5986637
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getcorversion-function"></a>GetCORVersion-Funktion
Gibt die Versionsnummer der common Language Runtime (CLR), die im aktuellen Prozess ausgeführt wird.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>Parameter  
 `pbuffer`  
 Ein Zeiger auf einen Puffer, in dem die CLR gibt eine Zeichenfolge, die Version der Laufzeit, die derzeit in den Prozess geladen wird. Die zurückgegebene Zeichenfolge hat das gleiche Format wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), z. B. "v1.0.1216". Wenn die Common Language Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.  
  
 `cchBuffer`  
 Die Anzahl der Zeichen (`WCHAR`s), können in gespeicherten werden `pbuffer`.  
  
 `dwLength`  
 Ein Zeiger auf die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `pbuffer`. Wenn `pbuffer` ist ein null-Zeiger, die Common Language Runtime gibt E_POINTER zurück. Wenn die Anzahl der Zeichen größer ist die Länge von `pbuffer` , gibt die Runtime ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
