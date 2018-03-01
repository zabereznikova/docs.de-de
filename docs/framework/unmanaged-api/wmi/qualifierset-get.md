---
title: QualifierSet_Get-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_Get Ruft einen benannten Qualifizierer ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93ba4e59dda4806931ba085f8c63b63a1d8bd797
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetget-function"></a>QualifierSet_Get-Funktion
Ruft den angegebenen benannten Qualifizierer ab.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`   
[in] Dieser Parameter wird nicht verwendet.

`ptr`   
[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.

`wszName`   
[in] Der Name des Qualifizierers der, deren Wert angefordert wird.

`lFlags`   
[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`   
[out] Bei erfolgreicher Ausführung, den richtigen Typ und Wert für den Qualifizierer. Wenn die Funktion fehlschlägt, die `VARIANT` verweist `pVal` wird nicht geändert. Wenn dieser Parameter ist `null`, der Parameter wird ignoriert.

`plFlavor`   
[out] Ein Zeiger auf einen Long-Wert, der die Qualifizierer Flavor Bits für den Qualifizierer des angeforderten empfängt. Dieser Parameter kann sein, wenn Flavor-Informationen nicht erwünscht ist, `null`. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Der angegebene Qualifizierer ist nicht vorhanden. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Get](https://msdn.microsoft.com/library/aa391867(v=vs.85).aspx) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
