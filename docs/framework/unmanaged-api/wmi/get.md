---
title: Get-Funktion (Referenz zur nicht verwalteten API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1f838c26d45c0f3cfbd50ac0ce02d234b82ddae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746659"
---
# <a name="get-function"></a>Get-Funktion

Ruft den angegebenen Eigenschaftswert ab, falls vorhanden.

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
[in] Dieser Parameter wird nicht verwendet.

`ptr`\
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszName`\
[in] Der Name der Eigenschaft.

`lFlags`\
[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`\
[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält Sie den Wert des der `wszName` Eigenschaft. Die `pval` Argument erhält, den richtigen Typ und Wert für den Qualifizierer.

`pvtType`\
[out] Wenn die Funktion erfolgreich zurückgegeben wird, enthält eine [CIM-Typ Konstante](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) , der den Eigenschaftentyp angibt. Der Wert kann auch sein `null`. 

`plFlavor`\
[out] Wenn die Funktion erfolgreich zurückgegeben wird, erhält Informationen über den Ursprung der Eigenschaft. Die Werte sind möglich `null`, oder eine der folgenden WBEM_FLAVOR_TYPE Konstanten definiert in der *WbemCli.h* Headerdatei: 

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Die Eigenschaft ist eine standard-Systemeigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt. <br> Für eine Instanz: Die Eigenschaft wurde während der von der übergeordneten Klasse geerbt nicht von der Instanz geändert.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: Die Eigenschaft gehört der abgeleiteten Klasse. <br> Für eine Instanz: Die Eigenschaft wird von der Instanz geändert werden. d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde. |

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein oder mehrere Parameter sind ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) Methode.

Die `Get` Funktion kann auch Systemeigenschaften zurückzugeben.

Die `pVal` Argument erhält, den richtigen Typ und Wert für den Qualifizierer und die COM- [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) Funktion

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** WMINet_Utils.idl

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
