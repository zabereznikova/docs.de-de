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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95cea4cb3e7e7df2b6b52256a440b9a8d544f2db
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798410"
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
[in] Reserviert. Dieser Parameter muss 0 sein.

`pstrName`\
vorgenommen Ein neuer `BSTR` , der den Eigenschaftsnamen enthält. Sie können diesen Parameter auf festlegen `null` , wenn der Name nicht erforderlich ist.

`pVal`\
vorgenommen Ein `VARIANT` , der mit dem Wert der-Eigenschaft ausgefüllt ist. Sie können diesen Parameter auf festlegen `null` , wenn der Wert nicht erforderlich ist. Wenn die Funktion einen Fehlercode zurückgibt, `VARIANT` bleibt der `pVal` an übergebenen unverändert unverändert.

`pvtType`\
vorgenommen Ein Zeiger auf eine `CIMTYPE` Variable (ein `LONG` -Objekt, in das der Typ der Eigenschaft eingefügt wird). Der Wert dieser Eigenschaft kann sein. in `VT_NULL_VARIANT`diesem Fall muss der tatsächliche Typ der Eigenschaft bestimmt werden. Dieser Parameter kann auch sein `null`.

`plFlavor`\
vorgenommen `null`oder ein Wert, der Informationen über den Ursprung der Eigenschaft empfängt. Mögliche Werte finden Sie im Abschnitt [Hinweise].

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Die [`BeginEnumeration`](beginenumeration.md) Funktion wurde nicht aufgerufen. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remote Prozedur Aufrufe zwischen dem aktuellen Prozess und der Windows-Verwaltung ist fehlgeschlagen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der-Enumeration sind keine weiteren Eigenschaften vorhanden. |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) -Methode.

Diese Methode gibt auch Systemeigenschaften zurück.

Wenn der zugrunde liegende Typ der Eigenschaft ein Objekt Pfad, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist, enthält der zurückgegebene Typ nicht genügend Informationen. Der Aufrufer muss `CIMTYPE` die-Eigenschaft für die angegebene Eigenschaft überprüfen, um zu bestimmen, ob die Eigenschaft ein Objekt Verweis, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist.

Wenn `plFlavor` `LONG` nicht `null`ist, empfängt der Wert Informationen über den Ursprung der Eigenschaft wie folgt:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Die-Eigenschaft ist eine Standardsystem Eigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt. <br> Für eine-Instanz: Die-Eigenschaft, die von der übergeordneten Klasse geerbt wurde, wurde von der-Instanz nicht geändert.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: Die-Eigenschaft gehört zur abgeleiteten Klasse. <br> Für eine-Instanz: Die-Eigenschaft wird von der-Instanz geändert. Das heißt, es wurde ein Wert angegeben, oder es wurde ein Qualifizierer hinzugefügt oder geändert. |

## <a name="requirements"></a>Anforderungen

**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** WMINet_Utils.idl

**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
