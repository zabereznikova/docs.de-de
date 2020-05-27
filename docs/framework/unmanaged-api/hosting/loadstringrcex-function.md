---
title: LoadStringRCEx-Funktion
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008512"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx-Funktion
Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `lcid`  
 in Ein Kultur Bezeichner. Übergeben Sie den Wert-1 für `lcid` , um die Standard Kultur zu verwenden.  
  
 `iResourceID`  
 [in] Ein HRESULT.  
  
 `szBuffer`  
 vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.  
  
 `iMax`  
 in Die Größe des Fehlermeldungs Puffers.  
  
 `bQuiet`  
 in Erten.  
  
 `pcwchUsed`  
 vorgenommen Ein Zeiger auf die Länge der Fehlermeldung.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt neben den folgenden Werten Standard-COM-Fehlercodes zurück, die in WinError. h definiert sind.  
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szBuffer`ist NULL, oder `iMax` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Methode nicht erfolgreich abgeschlossen wird, `szBuffer` enthält eine leere Zeichenfolge.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC-Funktion](loadstringrc-function.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
