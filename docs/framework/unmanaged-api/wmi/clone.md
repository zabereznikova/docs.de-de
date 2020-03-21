---
title: Klonfunktion (Nicht verwaltete API-Referenz)
description: Die Clone-Funktion gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.
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
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176850"
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`ppCopy`  
[out] Ein neues Objekt, das vollständig `ptr`einsam von ist. Dieses Argument `null` kann nicht sein, wenn es die Kopie des aktuellen Objekts empfängt.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `null`wurde als Parameter angegeben, und es ist in dieser Verwendung nicht legal. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um das Objekt zu klonen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Clone-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)

Das geklonte Objekt ist ein COM-Objekt mit einer Referenzanzahl von 1.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
