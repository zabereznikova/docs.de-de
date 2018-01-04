---
title: NextMethod-Funktion (Referenz zur nicht verwalteten API)
description: "Die NextMethod-Funktion ruft die nächste Methode in einer Enumeration ab."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b886b3ecbd1d5b5b8d212846b2bd8291fa43909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="nextmethod-function"></a>NextMethod-Funktion
Ruft eine Enumeration, die mit einem Aufruf von beginnt die nächste Methode [BeginMethodEnumeration](beginmethodenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pName`  
[out] Ein Zeiger, der auf zeigt `null` vor dem Aufruf. Wenn die Funktion zurückgibt, die Adresse eines neuen `BSTR` , enthält der Name der Methode. 

`ppSignatureIn`  
[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , enthält die `in` Parameter für die Methode. 

`ppSignatureOut`  
[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) , enthält die `out` Parameter für die Methode. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Es sind keine weiteren Eigenschaften in der Enumeration. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) Methode.

Der Aufrufer beginnt die Enumerationsfolge durch Aufrufen der [BeginMethodEnumeration](beginmethodenumeration.md) -Funktion, und klicken Sie dann die [NextMethod]-Funktion aufruft, bis die Funktion gibt `WBEM_S_NO_MORE_DATA`. Der Aufrufer abgeschlossen optional die Sequenz ist, durch den Aufruf [EndMethodEnumeration](endmethodenumeration.md). Der Aufrufer wird möglicherweise beendet, die Enumeration frühzeitig durch Aufrufen von [EndMethodEnumeration](endmethodenumeration.md) zu einem beliebigen Zeitpunkt.

## <a name="example"></a>Beispiel

Eine C++-Beispiel finden Sie unter der [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
