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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ec8e5dfc92a818bfc23c28f3058086c3bd1a8ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597943"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx-Funktion
Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `lcid`  
 [in] Ein Kulturbezeichner. Übergeben Sie-1 für `lcid` die Standardkultur verwenden.  
  
 `iResourceID`  
 [in] Ein HRESULT.  
  
 `szBuffer`  
 [out] Ein Puffer, der die Fehlermeldung nach dem erfolgreichen Abschluss enthält.  
  
 `iMax`  
 [in] Die Größe des Puffers für die Fehlermeldung.  
  
 `bQuiet`  
 [in] Ignoriert.  
  
 `pcwchUsed`  
 [out] Ein Zeiger auf die Länge der Fehlermeldung.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes, zurück, wie in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|`szBuffer` null ist, oder `iMax` ist 0 (null).|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Methode nicht erfolgreich abgeschlossen wird `szBuffer` enthält eine leere Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC-Funktion](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
