---
title: GetVersionFromProcess-Funktion
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452104939acf5de7bb151cba00d65fb6631c98d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124084"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess-Funktion
Ruft die Versionsnummer der die common Language Runtime (CLR), die dem angegebenen Prozesshandle zugeordnet ist.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hProcess`  
 [in] Ein Handle für einen Prozess.  
  
 `pVersion`  
 [out] Ein Puffer, der die Versionsnummer-Zeichenfolge nach dem erfolgreichen Abschluss der Methode enthält.  
  
 `cchBuffer`  
 [in] Die Länge des Versionspuffers.  
  
 `pdwLength`  
 [out] Ein Zeiger auf die Länge der die Versionsnummer-Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`pVersion` ist null und `cchBuffer` ist nicht null ist, oder umgekehrt.<br /><br /> - oder - <br /><br /> `hProcess` ist kein gültiges Handle an einen Prozess.<br /><br /> - oder - <br /><br /> Die CLR wird nicht geladen werden.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` ist null oder kleiner als die Länge der Versionszeichenfolge.|  
|E_NOTIMPL|Diese Methode ist nicht auf das Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetRequestedRuntimeInfo-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
