---
title: LoadStringRC-Funktion
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 66d4c14234c7929af443922f86098b46a4aa6eb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122019"
---
# <a name="loadstringrc-function"></a>LoadStringRC-Funktion
Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iResourceID`  
 in Ein HRESULT.  
  
 `szBuffer`  
 vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.  
  
 `iMax`  
 in Die Größe des Fehlermeldungs Puffers.  
  
 `bQuiet`  
 in Erten.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szBuffer` ist NULL, oder `iMax` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Methode nicht erfolgreich abgeschlossen wird, enthält `szBuffer` eine leere Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** "Mscoree. dll" und "mscorwert. dll". Verwenden Sie "mscoree. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [LoadStringRCEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
