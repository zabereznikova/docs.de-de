---
title: Next-Funktion (Referenz zur nicht verwalteten API)
description: Die Next-Funktion Ruft die Next-Eigenschaft in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c2a7fae32e82caae40a95bfdad10fa78082988ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726783"
---
# <a name="next-function"></a>Next-Funktion

Ruft die Next-Eigenschaft in einer Enumeration ab, die mit einem Aufrufen von [beginenumeration](beginenumeration.md)beginnt.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lFlags`\
[in]: Reserviert Dieser Parameter muss 0 sein.

`pstrName`\
vorgenommen Ein neuer `BSTR` , der den Eigenschaftsnamen enthält. Sie können diesen Parameter auf festlegen, `null` Wenn der Name nicht erforderlich ist.

`pVal`\
vorgenommen Ein, der `VARIANT` mit dem Wert der-Eigenschaft ausgefüllt ist. Sie können diesen Parameter auf festlegen, `null` Wenn der Wert nicht erforderlich ist. Wenn die Funktion einen Fehlercode zurückgibt, `VARIANT` bleibt der an übergebenen `pVal` unverändert unverändert.

`pvtType`\
vorgenommen Ein Zeiger auf eine `CIMTYPE` Variable (ein- `LONG` Objekt, in das der Typ der Eigenschaft eingefügt wird). Der Wert dieser Eigenschaft kann sein `VT_NULL_VARIANT` . in diesem Fall muss der tatsächliche Typ der Eigenschaft bestimmt werden. Dieser Parameter kann auch sein `null` .

`plFlavor`\
[out] `null` oder ein Wert, der Informationen über den Ursprung der Eigenschaft empfängt. Mögliche Werte finden Sie im Abschnitt [Hinweise].

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Die Funktion wurde nicht aufgerufen [`BeginEnumeration`](beginenumeration.md) . |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remote Prozedur Aufrufe zwischen dem aktuellen Prozess und der Windows-Verwaltung ist fehlgeschlagen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der-Enumeration sind keine weiteren Eigenschaften vorhanden. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) -Methode.

Diese Methode gibt auch Systemeigenschaften zurück.

Wenn der zugrunde liegende Typ der Eigenschaft ein Objekt Pfad, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist, enthält der zurückgegebene Typ nicht genügend Informationen. Der Aufrufer muss die- `CIMTYPE` Eigenschaft für die angegebene Eigenschaft überprüfen, um zu bestimmen, ob die Eigenschaft ein Objekt Verweis, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist.

Wenn `plFlavor` nicht ist `null` , `LONG` empfängt der Wert Informationen über den Ursprung der Eigenschaft wie folgt:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Die-Eigenschaft ist eine Standardsystem Eigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt. <br> Für eine-Instanz: die-Eigenschaft wurde von der-Instanz nicht geändert, während Sie von der übergeordneten Klasse geerbt wurde.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: die Eigenschaft gehört zur abgeleiteten Klasse. <br> Für eine-Instanz: die-Eigenschaft wird von der-Instanz geändert. Das heißt, es wurde ein Wert angegeben, oder es wurde ein Qualifizierer hinzugefügt oder geändert. |

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils. idl

**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
