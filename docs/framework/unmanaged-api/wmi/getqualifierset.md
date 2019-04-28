---
title: GetQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetQualifierSet-Funktion ruft den Qualifizierer aus, legen Sie für eine Klasse oder Instanz ab.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bf52fbf9552dc464d9c646f0a2b1bc01cf89c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723328"
---
# <a name="getqualifierset-function"></a>GetQualifierSet-Funktion
Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`ppQualSet`  
[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer des Klassenobjekts ermöglicht. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, wird ein neues Objekt nicht zurückgegeben wird und der Zeiger bleibt unverändert. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es wurde ein allgemeiner Fehler. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist `null`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) Methode. 

Die [IWbemQualifierSet Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lässt den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer. Eine solche hinzugefügt, bearbeitet oder gelöscht.-Qualifizierer gelten für die vollständige Definition der Instanz oder Klasse.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
