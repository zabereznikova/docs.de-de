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
ms.openlocfilehash: fbaf45da0902ded8a2f7bf0d470aaed3b5f531aa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617125"
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
|E_INVALIDARG|`pVersion`ist NULL und `cchBuffer` ist nicht NULL (oder umgekehrt).<br /><br /> - oder -<br /><br /> `hProcess`ist kein gültiges Handle für einen Prozess.<br /><br /> - oder -<br /><br /> Die CLR ist nicht geladen.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`ist NULL oder kleiner als die Länge der Versions Zeichenfolge.|  
|E_NOTIMPL|Diese Methode ist nicht im Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetRequestedRuntimeInfo-Funktion](getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion-Funktion](getrequestedruntimeversion-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
