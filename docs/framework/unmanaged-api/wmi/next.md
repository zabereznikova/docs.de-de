---
title: Next-Funktion (Referenz zur nicht verwalteten API)
description: "Die nächste Funktion Retireves die nächste Eigenschaft in einer Enumeration."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a>Next-Funktion
Ruft die nächste Eigenschaft in eine Enumeration, die mit einem Aufruf von beginnt [BeginEnumeration](beginenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pstrName`  
[out] Ein neues `BSTR` , die den Namen der Eigenschaft enthält. Legen Sie diesen Parameter, um `null` , wenn der Name nicht erforderlich ist.

`pVal`  
[out] Ein `VARIANT` mit dem Wert der Eigenschaft gefüllt. Legen Sie diesen Parameter, um `null` , wenn der Wert nicht erforderlich ist. Wenn die Funktion einen Fehlercode zurückgibt der `VARIANT` übergeben `pVal` ist der linke unverändert bleiben sollen. 

`pvtType`  
[out] Ein Zeiger auf eine `CIMTYPE` Variable (eine `LONG` in dem der Typ der Eigenschaft platziert ist). Der Wert dieser Eigenschaft kann eine `VT_NULL_VARIANT`, in diesem Fall ist es erforderlich, den tatsächlichen Typ der Eigenschaft zu ermitteln. Dieser Parameter kann auch `null`. 

`plFlavor`  
[out] `null`, oder ein Wert, der Informationen auf den Ursprung der Eigenschaft empfängt. Finden Sie im Abschnitt "Hinweise ["] mögliche Werte. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Ein allgemeiner Fehler ist aufgetreten. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf Schemakonflikt zwischen dem aktuellen Prozess und die Verwaltung von Windows ist fehlgeschlagen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Es sind keine weiteren Eigenschaften in der Enumeration. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) Methode.

Diese Methode gibt auch Systemeigenschaften zurück.

Wenn der zugrunde liegende Typ der Eigenschaft ein Objektpfad, ein Datum oder Uhrzeit oder einem anderen Sonderform ist, enthält der zurückgegebene Typ nicht genügend Informationen. Der Aufrufer muss die Untersuchung erfolgen die `CIMTYPE` für die angegebene Eigenschaft, um festzustellen, ob die Eigenschaft einen Objektverweis, ein Datum oder Uhrzeit oder eine andere Sonderform ist.

Wenn `plFlavor` nicht `null`die `LONG` Wert empfängt Informationen über den Ursprung der Eigenschaft, die wie folgt:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0 x 40 | Die Eigenschaft ist ein standard-Systemeigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0 x 20 | Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt. </br> Für eine Instanz: die Eigenschaft während der übergeordneten Klasse geerbt wurde nicht verändert von der Instanz.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: die Eigenschaft gehört der abgeleiteten Klasse. </br> Für eine Instanz: die Eigenschaft geändert wird, von der Instanz; d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde. |

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
