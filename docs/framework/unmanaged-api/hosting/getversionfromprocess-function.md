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
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721880"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess-Funktion

Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die dem angegebenen Prozess Handle zugeordnet ist.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `hProcess`  
 in Ein Handle für einen Prozess.  
  
 `pVersion`  
 vorgenommen Ein Puffer, der die Versionsnummern Zeichenfolge nach erfolgreichem Abschluss der Methode enthält.  
  
 `cchBuffer`  
 in Die Länge des Versions Puffers.  
  
 `pdwLength`  
 vorgenommen Ein Zeiger auf die Länge der Versionsnummern Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`pVersion` ist NULL und `cchBuffer` ist nicht NULL (oder umgekehrt).<br /><br /> - oder -<br /><br /> `hProcess` ist kein gültiges Handle für einen Prozess.<br /><br /> - oder -<br /><br /> Die CLR ist nicht geladen.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer` ist NULL oder kleiner als die Länge der Versions Zeichenfolge.|  
|E_NOTIMPL|Diese Methode ist nicht im Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetRequestedRuntimeInfo-Funktion](getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion-Funktion](getrequestedruntimeversion-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
