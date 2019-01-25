---
title: GetPropertyQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetPropertyQualifierSet-Funktion ruft ab, der Qualifizierer, die für eine Eigenschaft festgelegt wird.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec91a1f6fba70e3c9706541dc641ddd019d44841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642203"
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet-Funktion
Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`wszMethod`  
[in] Der Eigenschaftenname. `wszProperty` muss auf einen gültigen zeigen `LPCWSTR`. 

`ppQualSet`  
[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer der Eigenschaft ermöglicht. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger zum zeigen auf festgelegt ist `null`. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist `null`. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | Die Funktion versucht, Qualifizierer, der eine Systemeigenschaft abzurufen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) Methode. 

Ein Aufruf dieser Funktion werden nur dann, wenn das aktuelle Objekt mit der Definition einer CIM-Klasse ist. Bearbeitung der Methode ist nicht verfügbar für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Ponters, die auf das CIM-Instanzen verweisen.

Da jede Methode eine eigene Qualifizierer, möglicherweise die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.

Da Systemeigenschaften keine Qualifizierer verfügen, die Funktion gibt `WBEM_E_SYSTEM_PROPERTY` Wenn Sie versuchen, Sie erhalten eine [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Zeiger für eine Systemeigenschaft.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch
- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
