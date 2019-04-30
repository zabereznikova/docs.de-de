---
title: GetRequestedRuntimeVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee737f4c6d34e77996f5ba08ce4d84132a99238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985659"
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion-Funktion
Ruft die Versionsnummer der von der angegebenen Anwendung angeforderten die common Language Runtime (CLR) ab. Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.  
  
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
  
## <a name="parameters"></a>Parameter  
 `pExe`  
 [in] Der Name der Anwendung.  
  
 `pVersion`  
 [out] Ein Puffer, der die Versionsnummer-Zeichenfolge nach dem erfolgreichen Abschluss enthält.  
  
 `cchBuffer`  
 [in] Die Länge des Versionspuffers.  
  
 `pdwLength`  
 [out] Ein Zeiger auf die Länge der die Versionsnummer-Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Die Version-Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.|  
|E_POINTER|`pdwLength` ist NULL.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetRequestedRuntimeInfo-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
