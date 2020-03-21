---
title: Get-Funktion (Nicht verwaltete API-Referenz)
description: Die Get-Funktion ruft den angegebenen Eigenschaftswert ab.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174978"
---
# <a name="get-function"></a>Get-Funktion

Ruft den angegebenen Eigenschaftswert ab, sofern er vorhanden ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Parameter

`vFunc`\
[in] Dieser Parameter ist nicht verwendet.

`ptr`\
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`\
[in] Der Name der Eigenschaft.

`lFlags`\
[in]: Reserviert Dieser Parameter muss 0 sein.

`pVal`\
[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält den Wert der `wszName` Eigenschaft. Dem `pval` Argument wird der richtige Typ und Wert für den Qualifizierer zugewiesen.

`pvtType`\
[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Typkonstante,](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) die den Eigenschaftstyp angibt. Sein Wert kann `null`auch sein.

`plFlavor`\
[out] Wenn die Funktion erfolgreich zurückkehrt, erhält Informationen über den Ursprung der Eigenschaft. Sein Wert `null`kann , oder eine der folgenden WBEM_FLAVOR_TYPE konstanten sein, die in der *WbemCli.h-Headerdatei* definiert sind:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Die Eigenschaft ist eine Standard-Systemeigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt. <br> Für eine Instanz: Die Eigenschaft wurde zwar von der übergeordneten Klasse geerbt, aber von der Instanz nicht geändert.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: Die Eigenschaft gehört zur abgeleiteten Klasse. <br> Für eine Instanz: Die Eigenschaft wird von der Instanz geändert; D. h., es wurde ein Wert angegeben oder ein Qualifizierer hinzugefügt oder geändert. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeines Versagen aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Get-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get)

Die `Get` Funktion kann auch Systemeigenschaften zurückgeben.

Dem `pVal` Argument wird der richtige Typ und Wert für den Qualifizierer und die COM [VariantInit-Funktion](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) zugewiesen.

## <a name="requirements"></a>Requirements (Anforderungen)

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Kopfzeile:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
