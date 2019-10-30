---
title: Getqualifierset-Funktion (Referenz zur nicht verwalteten API)
description: Die getqualifierset-Funktion Ruft den Qualifizierer Satz für eine Klasse oder eine Instanz ab.
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
ms.openlocfilehash: 489e240af3f26e82f2459ac4b4dbd944639f78fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127437"
---
# <a name="getqualifierset-function"></a>Getqualifierset-Funktion
Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`ppQualSet`  
vorgenommen Empfängt den Schnittstellen Zeiger, der den Zugriff auf die Qualifizierer des Klassen Objekts zulässt. `ppQualSet` darf nicht `null` sein. Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger bleibt unverändert. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
|`WBEM_E_NOT_FOUND` | 0x80041002 angezeigt | Die angegebene Methode ist nicht vorhanden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist `null`. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getqualifierset](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) -Methode. 

Der [iwbemqualifierset-Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) ermöglicht dem Aufrufer, diese Qualifizierer hinzuzufügen, zu bearbeiten oder zu löschen. Solche hinzugefügten, bearbeiteten oder gelöschten Qualifizierer gelten für die gesamte-Instanz oder-Klassendefinition.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
