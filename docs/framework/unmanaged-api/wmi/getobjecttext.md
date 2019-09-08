---
title: Getobjecttext-Funktion (Referenz zur nicht verwalteten API)
description: Die getobjecttext-Funktion gibt ein Text Rendering eines Objekts in der MOF-Syntax zurück.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d47fcd59204a4d114fc9f0dc5bc4550ba1681f33
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798507"
---
# <a name="getobjecttext-function"></a>GetObjectText-Funktion
Gibt ein Text Rendering des-Objekts in der MOF-Syntax (Managed Object Format) zurück.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lFlags`  
in Normalerweise 0. Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0x1) angegeben ist, werden Qualifizierer ohne Weitergabeinformationen oder Informationen zur Konfiguration eingeschlossen.

`pstrObjectText`   
vorgenommen Ein Zeiger auf einen `null` bei Eintrag. Bei Rückgabe ein neu zugeordneter `BSTR` , das ein MOF-Syntax Rendering des-Objekts enthält.  

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Es ist ein allgemeiner Fehler aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getobjecttext](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) -Methode.

Der zurückgegebene MOF-Text enthält nicht alle Informationen über das Objekt, sondern nur genügend Informationen, damit der MOF-Compiler das ursprüngliche Objekt neu erstellen kann. Beispielsweise sind keine propagierten Qualifizierer oder Eigenschaften der übergeordneten Klasse enthalten.

Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:

1. Parameter werden in der Reihenfolge ihrer Bezeichnerwerte neu sequenziert.
1. Parameter, die als `[in]` und `[out]` angegeben werden, werden in einem einzelnen Parameter kombiniert.
 
`pstrObjectText`muss ein Zeiger auf einen `null` sein, wenn die-Funktion aufgerufen wird. Sie darf nicht auf eine Zeichenfolge verweisen, die vor dem Methodenaufruf gültig ist, da die Zuordnung des Zeigers nicht aufgehoben wird.

## <a name="requirements"></a>Anforderungen  
**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
