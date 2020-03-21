---
title: QualifierSet_Next -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Next-Funktion ruft den nächsten Qualifizierer in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174874"
---
# <a name="qualifierset_next-function"></a>QualifierSet_Next-Funktion
Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Parameter

`vFunc`[in] Dieser Parameter ist nicht verwendet.

`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`lFlags`[in] Reserviert. Dieser Parameter muss 0 sein.

`pstrName`[out] Der Name des Qualifizierers. Wenn `null`, wird dieser Parameter ignoriert. andernfalls `pstrName` sollte nicht auf `BSTR` einen gültigen oder einen Speicherverlust hinweisen. Wenn nicht null, weist die `BSTR` Funktion immer `WBEM_S_NO_ERROR`eine neue zu, wenn sie zurückgibt.

`pVal`[out] Wenn erfolgreich, der Wert für den Qualifizierer. Wenn die Funktion `VARIANT` fehlschlägt, `pVal` wird der spitz auf durch nicht geändert. Wenn dieser `null`Parameter ist , wird der Parameter ignoriert.

`plFlavor`[out] Ein Zeiger auf einen LONG, der die Qualifizierer-Variante erhält. Wenn Geschmacksinformationen nicht gewünscht werden, kann dieser Parameter . `null`

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Der Anrufer hat [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)nicht angerufen. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu starten. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der Enumeration sind keine weiteren Qualifizierer mehr übrig. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Next-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)

Sie rufen `QualifierSet_Next` die Funktion wiederholt auf, um alle Qualifizierer aufzuzählen, bis die Funktion zurückkehrt. `WBEM_S_NO_MORE_DATA` Um die Enumeration vorzeitig zu beenden, rufen Sie die [QualifierSet_EndEnumeration-Funktion](qualifierset-endenumeration.md) auf.

Die Reihenfolge der Qualifizierer, die während der Enumeration zurückgegeben werden, ist nicht definiert.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
