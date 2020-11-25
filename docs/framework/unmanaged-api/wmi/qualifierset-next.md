---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Next-Funktion Ruft den nächsten Qualifizierer in einer Enumeration ab.
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
ms.openlocfilehash: 54d79a3dc081e9cdcb42153b6f7aa457557e3399
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721126"
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

`vFunc` in Dieser Parameter wird nicht verwendet.

`ptr` in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`lFlags` in Bleiben. Dieser Parameter muss 0 sein.

`pstrName` vorgenommen Der Name des Qualifizierers. Wenn der `null` Wert ist, wird dieser Parameter ignoriert; andernfalls `pstrName` sollte nicht auf einen gültigen `BSTR` oder ein Speicherfehler hindeuten. Wenn der Wert nicht NULL ist, ordnet die Funktion immer einen neuen zu, `BSTR` Wenn Sie zurückgegeben wird `WBEM_S_NO_ERROR` .

`pVal` vorgenommen Bei Erfolg der Wert für den Qualifizierer. Wenn die Funktion fehlschlägt, `VARIANT` wird die, auf die von verwiesen `pVal` wird, nicht geändert. Wenn dieser Parameter ist `null` , wird der-Parameter ignoriert.

`plFlavor` vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifiziererkonfiguration empfängt. Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter sein `null` .

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Der Aufrufer hat [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)nicht aufgerufen. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der-Enumeration verbleiben keine weiteren Qualifizierer. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) -Methode.

Sie müssen die `QualifierSet_Next` Funktion wiederholt aufzählen, um alle Qualifizierer aufzulisten, bis die Funktion zurückgibt `WBEM_S_NO_MORE_DATA` . Um die Enumeration frühzeitig zu beenden, müssen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) -Funktion aufzurufen.

Die Reihenfolge der während der-Enumeration zurückgegebenen Qualifizierer ist nicht definiert.

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
