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
ms.openlocfilehash: 9dae3f1403d33aaf3cfb87d17856640548a90b4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688940"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader-Funktion

Erstellt einen Verlaufs Leser für die angegebene Datei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>Parameter  

 `wzFilePath`  
 in Der Dateipfad.  
  
 `ppHistoryReader`  
 vorgenommen Nach erfolgreichem Abschluss enthält einen Zeiger auf den Verlaufs Leser.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt zusätzlich zu den in der folgenden Tabelle beschriebenen Werten com-Standard Fehlercodes zurück, die in WinError. h definiert sind.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Gibt an, dass die Methode erfolgreich abgeschlossen wurde.|  
|E_INVALIDARG|Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen NULL-Verweis festgelegt ist.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Bibliothek:** Fusion.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
