---
title: Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Get-Funktion Ruft den angegebenen Eigenschafts Wert ab.
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
ms.openlocfilehash: 60f29b91000fd3c07efea88dcc319eb283a4af78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120324"
---
# <a name="get-function"></a>Get-Funktion

Ruft den angegebenen Eigenschafts Wert ab, falls vorhanden.

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
in Dieser Parameter wird nicht verwendet.

`ptr`\
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`wszName`\
in Der Name der Eigenschaft.

`lFlags`\
[in]: Reserviert Dieser Parameter muss 0 sein.

`pVal`\
vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, enthält Sie den Wert der `wszName`-Eigenschaft. Dem `pval`-Argument werden der richtige Typ und der richtige Wert für den Qualifizierer zugewiesen.

`pvtType`\
vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Type-Konstante](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) , die den Eigenschaftentyp angibt. Der Wert kann auch `null`werden. 

`plFlavor`\
vorgenommen Wenn die Funktion erfolgreich zurückgegeben wird, empfängt Informationen über den Ursprung der Eigenschaft. Der Wert kann `null`oder eine der folgenden WBEM_FLAVOR_TYPE-Konstanten sein, die in der Header Datei " *wbemcli. h* " definiert sind: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Die-Eigenschaft ist eine Standardsystem Eigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt. <br> Für eine-Instanz: die-Eigenschaft wurde von der-Instanz nicht geändert, während Sie von der übergeordneten Klasse geerbt wurde.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: die Eigenschaft gehört zur abgeleiteten Klasse. <br> Für eine-Instanz: die-Eigenschaft wird von der-Instanz geändert. Das heißt, es wurde ein Wert angegeben, oder es wurde ein Qualifizierer hinzugefügt oder geändert. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) -Methode.

Die `Get`-Funktion kann auch Systemeigenschaften zurückgeben.

Dem `pVal`-Argument werden der richtige Typ und Wert für den Qualifizierer und die com- [variantit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) -Funktion zugewiesen.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** WMINet_Utils. idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
