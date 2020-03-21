---
title: PutMethod-Funktion (Nicht verwaltete API-Referenz)
description: Die PutMethod-Funktion erstellt eine Methode.
ms.date: 11/06/2017
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174913"
---
# <a name="putmethod-function"></a>PutMethod-Funktion
Erstellt eine Methode.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*  ptr,
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`  
[in] Der Name der zu erstellenden Methode.

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`pSignatureIn`  
[in] Ein Zeiger auf eine Kopie der __Parameters `in` [Systemklasse,](/windows/desktop/WmiSdk/--parameters) die die Parameter für die Methode enthält. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.  

`pSignatureOut`  
[in]  Ein Zeiger auf eine Kopie der __Parameters `out` [Systemklasse,](/windows/desktop/WmiSdk/--parameters) die die Parameter für die Methode enthält. Dieser Parameter wird ignoriert, wenn er auf `null`festgelegt ist.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Mindestens ein Parameter ist ungültig. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Der `[in, out]` in den *pInSignature-* und *pOutSignature-Objekten* angegebene Methodenparameter weist unterschiedliche Qualifizierer auf.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Ein Methodenparameter fehlt die **ID** Spezifikation des ID-Qualifizierers. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Die ID-Serie, die den Methodenparametern zugewiesen ist, ist nicht aufeinander folgend oder beginnt nicht bei 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Der Rückgabewert für eine **ID** Methode verfügt über einen ID-Qualifizierer. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Es wurde versucht, einen vorhandenen Methodennamen aus einer übergeordneten Klasse wiederzuverwenden, und die Signaturen stimmen nicht überein. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::PutMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)

Dieser Methodenaufruf wird `ptr` nur unterstützt, wenn es sich um eine CIM-Klassendefinition handelt. Die Methodenmanipulation ist von [IWbemClassObject-Zeigern, die](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf CIM-Instanzen verweisen, nicht verfügbar.

Benutzer können keine Methoden mit Namen erstellen, die mit einem Unterstrich beginnen oder enden. Dies ist für Systemklassen und Eigenschaften reserviert.

Bei einer Methode `in` `out` werden die und parameter als Eigenschaften in [IWbemClassObject-Objekten](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) beschrieben.

Ein `[in/out]` Parameter kann definiert werden, indem beide Objekte, `pInSignature` `pOutSignature` auf die durch die und Parameter verwiesen wird, dieselbe Eigenschaft hinzufügen. In diesem Fall haben die **ID** Eigenschaften denselben ID-Qualifiziererwert.

Jede Eigenschaft [__Parameters](/windows/desktop/WmiSdk/--parameters) in einem __Parameters `ReturnValue` Klassenobjekts außer muss über einen ID-Qualifizierer verfügen, einen nullbasierten numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden. **ID** Es können keine zwei Parameter denselben **ID-Wert** haben, und kein **ID-Wert** kann übersprungen werden. Wenn eine der `PutMethod` beiden `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`Bedingungen auftritt, gibt die Funktion zurück.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter die [IWbemClassObject::PutMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
