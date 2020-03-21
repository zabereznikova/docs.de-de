---
title: DeleteMethod-Funktion (Nicht verwaltete API-Referenz)
description: Die DeleteMethod-Funktion löscht die angegebene Methode aus einer CIM-Klassendefinition.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174991"
---
# <a name="deletemethod-function"></a>DeleteMethod-Funktion
Löscht die angegebene Methode aus einer CIM-Klassendefinition.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`  
[in] Der Name der Methode, die aus der Klassentabelle entfernt werden soll. `wszName`muss ein Zeiger auf `LPCWSTR`eine gültige sein.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es steht nicht genügend Arbeitsspeicher zur Verfügung, um den Vorgang durchzuführen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |

## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::DeleteMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod)

Das Löschen von Methoden wird für [IWbemClassObject-Zeiger, die](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf CIM-Instanzen verweisen, nicht unterstützt.

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
