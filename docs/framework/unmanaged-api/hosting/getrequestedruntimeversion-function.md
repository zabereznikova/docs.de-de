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
ms.openlocfilehash: 6c16b02a5ae323ba80d44937f322810022dfa9f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711636"
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion-Funktion

Ruft die Versionsnummer der von der angegebenen Anwendung angeforderten Common Language Runtime (CLR) ab. Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pExe`  
 in Der Name der Anwendung.  
  
 `pVersion`  
 vorgenommen Ein Puffer, der nach erfolgreichem Abschluss die Zeichenfolge der Versionsnummer enthält.  
  
 `cchBuffer`  
 in Die Länge des Versions Puffers.  
  
 `pdwLength`  
 vorgenommen Ein Zeiger auf die Länge der Versionsnummern Zeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|ERROR_INSUFFICIENT_BUFFER|Der Versions Puffer ist nicht groß genug, um die Versions Zeichenfolge zu speichern.|  
|E_POINTER|`pdwLength` ist NULL.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetRequestedRuntimeInfo-Funktion](getrequestedruntimeinfo-function.md)
- [GetVersionFromProcess-Funktion](getversionfromprocess-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
