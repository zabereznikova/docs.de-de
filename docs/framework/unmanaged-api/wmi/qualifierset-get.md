---
title: QualifierSet_Get -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Get-Funktion ruft einen benannten Qualifizierer ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174887"
---
# <a name="qualifierset_get-function"></a>QualifierSet_Get-Funktion
Ruft den angegebenen benannten Qualifizierer ab.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Parameter

`vFunc`[in] Dieser Parameter ist nicht verwendet.

`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`wszName`[in] Der Name des Qualifizierers, dessen Wert angefordert wird.

`lFlags`[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`[out] Wenn erfolgreich, der richtige Typ und Wert für den Qualifizierer. Wenn die Funktion `VARIANT` fehlschlägt, `pVal` wird der spitz auf durch nicht geändert. Wenn dieser `null`Parameter ist , wird der Parameter ignoriert.

`plFlavor`[out] Ein Zeiger auf einen LONG, der die Qualifizierer-Geschmackbits für den angeforderten Qualifizierer empfängt. Wenn Geschmacksinformationen nicht gewünscht werden, kann dieser Parameter . `null`

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Qualifizierer ist nicht vorhanden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Get-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
