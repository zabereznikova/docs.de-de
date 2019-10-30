---
title: Klon Funktion (Referenz zur nicht verwalteten API)
description: Die Clone-Funktion gibt ein neues-Objekt zurück, das ein kompletter Klon der aktuellen ist.
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
ms.openlocfilehash: c8e7781a3efe7679ef2e05747862911db88bcc5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141614"
---
# <a name="clone-function"></a>Clone-Funktion
Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`ppCopy`  
vorgenommen Ein neues-Objekt, das eine komplette `ptr`ist. Dieses Argument kann nicht `null` werden, wenn es die Kopie des aktuellen-Objekts empfängt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `null` wurde als Parameter angegeben und ist in dieser Verwendung nicht zulässig. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um das Objekt zu klonen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) -Methode.

Das geklonte Objekt ist ein COM-Objekt mit einem Verweis Zähler von 1.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
