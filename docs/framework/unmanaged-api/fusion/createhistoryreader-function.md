---
title: CreateHistoryReader-Funktion
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132261"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader-Funktion
Erstellt einen Verlauf Leser für die angegebene Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parameter  
 `wzFilePath`  
 [in] Der Dateipfad.  
  
 `ppHistoryReader`  
 [out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes zurück, wie definiert in "Winerror.h", zusätzlich zu den Werten in der folgenden Tabelle beschrieben.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Gibt an, dass die Methode erfolgreich abgeschlossen.|  
|E_INVALIDARG|Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen null-Verweis festgelegt sind.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Bibliothek:** Fusion.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
