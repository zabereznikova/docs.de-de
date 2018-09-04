---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Next-Funktion ruft den nächsten Qualifizierer in einer Enumeration ab.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 938044a4e932139eb8a4d0a5d2f998cbc6f193cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507692"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next-Funktion
Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
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
[in] Dieser Parameter wird nicht verwendet.

`ptr`   
[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.

`lFlags`   
[in] Reserviert. Dieser Parameter muss 0 sein.

`pstrName`   
[out] Der Name des Qualifizierers. Wenn `null`, dieser Parameter wird ignoriert, andernfalls `pstrName` sollten verweist nicht auf einen gültigen `BSTR` oder ein Speicherverlust auftritt. Wenn nicht null ist, die Funktion immer eine neue zuordnet `BSTR` Wenn gibt `WBEM_S_NO_ERROR`.

`pVal`   
[out] Bei erfolgreicher Ausführung der Wert für den Qualifizierer. Wenn die Funktion fehlschlägt, die `VARIANT` verweist `pVal` wird nicht geändert. Wenn dieser Parameter ist `null`, der Parameter wird ignoriert.

`plFlavor`   
[out] Ein Zeiger auf einen Long-Wert, der die Qualifizierertyp empfängt. Dieser Parameter kann sein, wenn der Typ-Informationen nicht gewünscht ist, `null`. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Der Aufrufer nicht aufrufen [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Keine weitere Qualifizierer bleiben in der Enumeration. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) Methode.

Rufen Sie die `QualifierSet_Next` Funktion mehrmals, um alle Qualifizierer erst die Funktionsrückgabe aufzählen `WBEM_S_NO_MORE_DATA`. Um die Enumeration zu einem frühen Zeitpunkt zu beenden, rufen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) Funktion.

Die Reihenfolge der Qualifizierer, die zurückgegeben werden, während der Enumeration ist nicht definiert.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
