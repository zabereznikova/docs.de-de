---
title: GetRequestedRuntimeVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersion
helpviewer_keywords: GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfac4e32841b8a8332a1f4124c1326f1ef7da1f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion-Funktion
Ruft die Versionsnummer der von der angegebenen Anwendung angefordert der common Language Runtime (CLR) ab. Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pExe`  
 [in] Der Name der Anwendung.  
  
 `pVersion`  
 [out] Ein Puffer, der nach dem erfolgreichen Abschluss die Versionsnummernzeichenfolge enthält.  
  
 `cchBuffer`  
 [in] Die Länge des Versionspuffers.  
  
 `pdwLength`  
 [out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Die Version Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.|  
|E_POINTER|`pdwLength` ist NULL.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [GetRequestedRuntimeInfo-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
