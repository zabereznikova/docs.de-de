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
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697624"
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory-Funktion
Ruft den Pfad des Anwendungsverzeichnisses Verlauf.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wzDir`  
 [out] Ein Puffer, die den Pfad zum Anwendungsverzeichnis Verlauf enthalten soll.  
  
 `pdwSize`  
 [in, out] Die Länge des Puffers.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes, zurück, wie in der Datei "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`wzDir` oder `pdwSize` ist Null, oder die Version Zeichenfolge ist falsch.|  
  
## <a name="remarks"></a>Hinweise  
 Bei erfolgreichem Abschluss der `pdwSize` Argument auf die Länge der Zeichenfolge für den Pfad festgelegt ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Fusion.h  
  
 **Bibliothek:** Fusion.dll und "Mscorwks.dll". Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [CreateHistoryReader-Funktion](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [NukeDownloadedCache-Funktion](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
