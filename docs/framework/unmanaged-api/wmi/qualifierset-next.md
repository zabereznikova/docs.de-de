---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Next-Funktion Ruft den nächsten Qualifizierer in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141723"
---
# <a name="qualifierset_next-function"></a>QualifierSet_Next-Funktion
Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`   
in Dieser Parameter wird nicht verwendet.

`ptr`   
in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.

`lFlags`   
[in]: Reserviert Dieser Parameter muss 0 sein.

`pstrName`   
vorgenommen Der Name des Qualifizierers. Wenn `null`, wird dieser Parameter ignoriert. Andernfalls sollten `pstrName` nicht auf einen gültigen `BSTR` zeigen, oder es kommt zu einem Speicherfehler. Wenn der Wert nicht NULL ist, ordnet die Funktion immer eine neue `BSTR` zu, wenn Sie `WBEM_S_NO_ERROR`zurückgibt.

`pVal`   
vorgenommen Bei Erfolg der Wert für den Qualifizierer. Wenn die Funktion fehlschlägt, wird die `VARIANT`, auf die `pVal` verweist, nicht geändert. Wenn dieser Parameter `null`ist, wird der-Parameter ignoriert.

`plFlavor`   
vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifiziererkonfiguration empfängt. Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter `null`werden. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Der Aufrufer hat [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)nicht aufgerufen. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der-Enumeration verbleiben keine weiteren Qualifizierer. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) -Methode.

Sie können die `QualifierSet_Next`-Funktion wiederholt aufzählen, um alle Qualifizierer aufzulisten, bis die Funktion `WBEM_S_NO_MORE_DATA`zurückgibt. Um die Enumeration frühzeitig zu beenden, nennen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) -Funktion.

Die Reihenfolge der während der-Enumeration zurückgegebenen Qualifizierer ist nicht definiert.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
