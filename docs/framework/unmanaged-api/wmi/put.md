---
title: Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Put-Funktion weist einen neuen Wert an eine benannte Eigenschaft an.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09d3edc74b34688d5cc36e688f634850cfb60910
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="put-function"></a>Put-Funktion
Legt eine benannte Eigenschaft auf einen neuen Wert fest.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszName`  
[in] Der Name der Eigenschaft. Dieser Parameter darf nicht sein `null`.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pVal`   
[in] Ein Zeiger auf eine gültige `VARIANT` , wird der neue Eigenschaftswert. Wenn `pVal` ist `null` oder verweist auf eine `VARIANT` des Typs `VT_NULL`, die Eigenschaft wird festgelegt, um `null`. 

`vtType`  
[in] Der Typ des `VARIANT` verweist `pVal`. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.
 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | Ein allgemeiner Fehler ist aufgetreten. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Einen oder mehrere Parameter sind ungültig. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Der Eigenschaftentyp wird nicht erkannt. Dieser Wert wird zurückgegeben, wenn Klasseninstanzen zu erstellen, wenn die Klasse bereits besteht. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Für Instanzen: Gibt an, dass `pVal` verweist auf eine `VARIANT` mit einem falschen Typ für die Eigenschaft. <br/> Für Klassendefinitionen: die Eigenschaft bereits vorhanden ist, in der übergeordneten Klasse und der neue COM-Typ unterscheidet sich von der alten COM-Typ. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) Methode.

Diese Funktion überschreibt immer den aktuellen Eigenschaftenwert durch ein neues. Wenn die [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) verweist auf eine Klassendefinition `Put` erstellt oder aktualisiert den Wert der Eigenschaft. Wenn [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) verweist auf eine CIM-Instanz `Put` aktualisiert den Wert der Eigenschaft nur; `Put` einen Eigenschaftswert kann nicht erstellt werden.

Die `__CLASS` Systemeigenschaft überschreibbar nur während der klassenerstellung, wenn er nicht leer sein kann. Alle anderen Systemeigenschaften sind schreibgeschützt.

Ein Benutzer kann keine Eigenschaften mit Namen erstellen, die mit einem Unterstrich ("_") beginnen oder enden. Dies ist für Systemklassen und Eigenschaften reserviert.

Wenn die Eigenschaft festgelegt wird, indem Sie die `Put` Funktion, die in der übergeordneten Klasse vorhanden ist, wird der Standardwert der Eigenschaft wird geändert, es sei denn, der Eigenschaftstyp nicht den Typ der übergeordneten Klasse übereinstimmt. Wenn die Eigenschaft ist nicht vorhanden, und es kein Typenkonflikt ist, ist die Eigenschaft Ceated.

Verwenden der `vtType` Parameters nur beim Erstellen von neuer Eigenschaften in einer CIM-Klassendefinition und `pVal` ist `null` oder verweist auf eine `VARIANT` vom Typ `VT_NULL`. In diesem Fall die `vType` Parameter gibt den CIM-Typ der Eigenschaft. In allen anderen Fällen `vtType` muss 0 sein. `vtType`muss auch 0 sein, wenn das zugrunde liegende Objekt eine Instanz ist (auch wenn `Val` ist `null`), da der Typ der Eigenschaft unveränderlich ist und kann nicht geändert werden.   

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie die [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
