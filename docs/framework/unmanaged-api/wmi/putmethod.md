---
title: PutMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die PutMethod-Funktion erstellt eine Methode an.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca510f30f0f38ae54eb83046b0e9d5541db882d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758692"
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
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszName`  
[in] Der Name der Methode zu erstellen. 

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pSignatureIn`  
[in] Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](/windows/desktop/WmiSdk/--parameters) , enthält die `in` Parameter für die Methode. Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.  

`pSignatureOut`  
[in]  Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](/windows/desktop/WmiSdk/--parameters) , enthält die `out` Parameter für die Methode. Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein oder mehrere Parameter sind ungültig. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Die `[in, out]` Methodenparameter angegeben wird, sowohl die *pInSignature* und *pOutSignature* Objekte verfügen über unterschiedliche Qualifizierer.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Parameter der Methode fehlt die Angabe der **ID** Qualifizierer. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Die ID-Reihe, die die Parameter der Methode zugewiesen ist, nicht aufeinander folgende oder beginnt nicht bei 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Der Rückgabewert für eine Methode hat eine **ID** Qualifizierer. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Es wurde versucht, einen vorhandenen Methodennamen einer übergeordneten Klasse wiederverwendet, und die Signaturen stimmten nicht überein. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) Methode.

Dieser Methodenaufruf wird nur unterstützt, wenn `ptr` ist die Definition einer CIM-Klasse. Bearbeitung der Methode ist nicht verfügbar [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf das CIM-Instanzen verweisen.

Benutzer können keine Methoden mit Namen erstellen, die mit einem Unterstrich beginnen oder enden. Dies ist für die Systemklassen und Eigenschaften reserviert.

Für eine Methode die `in` und `out` Parameter werden als Eigenschaften in beschrieben [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Objekte.

Ein `[in/out]` Parameter definiert werden, indem Sie die gleiche Eigenschaft hinzufügen, auf beide Objekte verweist die `pInSignature` und `pOutSignature` Parameter. In diesem Fall die Eigenschaften verwenden dieselbe **ID** Wert des Qualifizierers.

Jede Eigenschaft im eine [__Parameters](/windows/desktop/WmiSdk/--parameters) Objekt außer Klasse `ReturnValue` benötigen eine **ID** Qualifizierer, eine nullbasierte numerischer Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden. Keine zwei Parameter haben den gleichen **ID** Wert und keine **ID** Wert übersprungen werden kann. Wenn eine der Bedingungen auftritt, die `PutMethod` -Funktion zurückgegeben `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie unter den [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
