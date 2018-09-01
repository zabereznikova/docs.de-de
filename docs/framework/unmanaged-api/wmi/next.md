---
title: Die Next-Funktion (Referenz zur nicht verwalteten API)
description: Die nächste Funktion Retireves die nächste Eigenschaft in einer Enumeration.
ms.date: 11/06/2017
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
ms.openlocfilehash: 15d470ccf9384695aa38a50c2c062c1b660fea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388613"
---
# <a name="next-function"></a>Die Next-Funktion
Ruft die nächste Eigenschaft in einer Enumeration, die mit einem Aufruf von beginnt [BeginEnumeration](beginenumeration.md).  

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
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pstrName`  
[out] Ein neues `BSTR` , die den Eigenschaftsnamen enthält. Sie können diesen Parameter festlegen, um `null` Wenn der Name nicht erforderlich ist.

`pVal`  
[out] Ein `VARIANT` mit dem Wert der Eigenschaft gefüllt. Sie können diesen Parameter festlegen, um `null` Wenn der Wert nicht erforderlich ist. Wenn die Funktion einen Fehlercode zurückgibt. die `VARIANT` übergeben `pVal` wird links unverändert. 

`pvtType`  
[out] Ein Zeiger auf eine `CIMTYPE` Variable (eine `LONG` in dem der Typ der Eigenschaft befindet). Der Wert dieser Eigenschaft kann sein ein `VT_NULL_VARIANT`, in diesem Fall ist es erforderlich, um zu bestimmen, den tatsächlichen Typ der Eigenschaft. Dieser Parameter kann auch sein `null`. 

`plFlavor`  
[out] `null`, oder ein Wert, der Informationen auf den Ursprung der Eigenschaft empfängt. Finden Sie im Abschnitt "[" Hinweise "]" für die möglichen Werte. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | Es wurde ein allgemeiner Fehler. |
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Der Remoteprozeduraufruf zwischen dem aktuellen Prozess und die Windows-Verwaltung ist fehlgeschlagen. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Es gibt keine weiteren Eigenschaften in der Enumeration. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) Methode.

Diese Methode gibt auch Systemeigenschaften zurück.

Wenn der zugrunde liegende Typ der Eigenschaft eines Objektpfad, ein Datum oder Uhrzeit oder einen anderen speziellen Typ ist, enthält der zurückgegebene Typ keine ausreichende Informationen. Der Aufrufer muss Untersuchen der `CIMTYPE` für die angegebene Eigenschaft aus, um festzustellen, ob die Eigenschaft einen Objektverweis, ein Datum oder Uhrzeit oder einen anderen speziellen Typ ist.

Wenn `plFlavor` nicht `null`, `LONG` Wert empfängt Informationen über den Ursprung der Eigenschaft, die wie folgt:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0 x 40 | Die Eigenschaft ist eine standard-Systemeigenschaft. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt. </br> Für eine Instanz: die Eigenschaft, während von der übergeordneten Klasse geerbt wurde nicht geändert von der Instanz.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Für eine Klasse: die Eigenschaft gehört, in die abgeleitete Klasse. </br> Für eine Instanz: die Eigenschaft wird geändert, indem die Instanz d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde. |

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
