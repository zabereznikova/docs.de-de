---
title: GetHistoryFileDirectory-Funktion
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796853"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory-Funktion
Ruft den Pfad des Verzeichnisses für den Anwendungs Verlauf ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wzDir`  
 vorgenommen Ein Puffer, der den Pfad zum Anwendungs Verlaufs Verzeichnis enthalten soll.  
  
 `pdwSize`  
 [in, out] Die Länge des Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt Standard-COM-Fehlercodes zurück, die in der Datei "Winerror. h" zusätzlich zu den folgenden Werten definiert sind.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`wzDir`oder `pdwSize` ist NULL, oder die Versions Zeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Hinweise  
 Nach erfolgreichem Abschluss wird `pdwSize` das-Argument auf die Länge der Pfad Zeichenfolge festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Fern** "Fusion. dll" und "mscorwert. dll". Verwenden Sie "Fusion. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CreateHistoryReader-Funktion](createhistoryreader-function.md)
- [NukeDownloadedCache-Funktion](nukedownloadedcache-function.md)
- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
