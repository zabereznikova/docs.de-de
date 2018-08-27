---
title: Clone-Funktion (Referenz zur nicht verwalteten API)
description: Die Klon-Funktion gibt es sich um ein neues Objekt, das einen Klon der aktuellen Aktivität abgeschlossen ist.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd87cb619ef2dc1e0548c7553585b7e51e94c4f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924774"
---
# <a name="clone-function"></a>Clone-Funktion
Gibt ein neues Objekt, das eine vollständige Klon des aktuellen Objekts ist.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`ppCopy`  
[out] Ein neues Objekt, das eine vollständige ist der einzelne `ptr`. Dieses Argument nicht `null` empfängt er die Kopie des aktuellen Objekts.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | `null` als Parameter angegeben wurde, und es ist nicht zulässig, bei dieser Verwendung. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zur Verfügung, um das Objekt zu klonen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) Methode.

Das geklonte Objekt ist ein COM-Objekt mit einer Verweisanzahl von 1.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
