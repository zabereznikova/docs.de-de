---
title: Endmethodenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die endmethodenumeration-Funktion beendet eine enumerationssequenz der Methode.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 174cf76d4b0ddf07e67e02bff20a983dca08819a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132021"
---
# <a name="endmethodenumeration-function"></a>EndMethodEnumeration-Funktion
Beendet eine enumerationssequenz, die mit einem Aufrufen der [beginmethodenumeration-Funktion](beginmethodenumeration.md)gestartet wurde.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | 0x8004101d | Interner Fehler. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: endmethodenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) -Methode.

Der Aufrufer startet die enumerationssequenz mithilfe der [beginmethodenumeration-Funktion](beginmethodenumeration.md)und ruft dann die [nextmethod-Funktion](nextmethod.md )auf, bis die Methode `WBEM_S_NO_MORE_DATA`zurückgibt. Der Aufrufer schließt die Sequenz optional durch Aufrufen von `EndMethodEnumeration`ab. Der Aufrufer kann die Enumeration frühzeitig beenden, indem `EndMethodEnumeration` jederzeit aufgerufen wird.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
