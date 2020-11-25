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
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727548"
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
 [in] Ein HRESULT.  
  
 `szBuffer`  
 vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.  
  
 `iMax`  
 in Die Größe des Fehlermeldungs Puffers.  
  
 `bQuiet`  
 in Erten.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szBuffer` ist NULL oder `iMax` ist NULL (0).|  
  
## <a name="remarks"></a>Hinweise  

 Wenn die Methode nicht erfolgreich abgeschlossen wird, `szBuffer` enthält eine leere Zeichenfolge.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** MSCorEE.dll und Mscorwks.dll. Verwenden Sie MSCorEE.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [LoadStringRCEx-Funktion](loadstringrcex-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
