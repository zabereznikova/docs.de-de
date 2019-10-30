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
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108611"
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
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Gibt an, dass die Methode erfolgreich abgeschlossen wurde.|  
|E_INVALIDARG|Gibt an, dass `wzFilePath` oder `ppHistoryReader` auf einen NULL-Verweis festgelegt sind.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Bibliothek:** Fusion. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Fusion: Globale statistische Funktionen](fusion-global-static-functions.md)
