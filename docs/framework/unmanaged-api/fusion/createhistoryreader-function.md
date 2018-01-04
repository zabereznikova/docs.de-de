---
title: CreateHistoryReader-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab5e54735c360cb7bd2e681c04b0b1ae491bd716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader-Funktion
Erstellt einen Leser Verlauf für die angegebene Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `wzFilePath`  
 [in] Der Dateipfad.  
  
 `ppHistoryReader`  
 [out] Bei erfolgreichem Abschluss können Sie einen Zeiger auf den Verlaufsreader enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den Werten in der folgenden Tabelle beschrieben.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Gibt an, dass die Methode erfolgreich abgeschlossen wurde.|  
|E_INVALIDARG|Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf ein null-Verweis festgelegt sind.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Bibliothek:** Fusion.dll  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
