---
title: GetMethod-Funktion (Referenz zur nicht verwalteten API)
description: GetMethod-Funktion ruft Informationen zu einer Methode ab.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethod
helpviewer_keywords: GetMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4e89dabb7f4542a63260445ff2d70edcafc1784
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="getmethod-function"></a>GetMethod-Funktion
Ruft Informationen über die angegebene Methode ab.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszName`  
[in] Der Methodenname. Dieser Parameter darf nicht sein `null` muss einem gültigen zeigen `LPCWSTR`.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`ppInSignature`   
[out] Ein Zeiger auf die Adresse des ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) -Instanz, die in Paramteers an die Methode beschreibt. Dieser Parameter wird ignoriert, wenn er, um festgelegt ist `null`. 

`ppOutSignature`  
[out] Ein Zeiger auf die Adresse des ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz, die die Out-Parameter an die Methode beschreibt. Dieser Parameter wird ignoriert, wenn er, um festgelegt ist `null`. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Die angegebene Eigenschaft wurde nicht gefunden. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) Methode.

Verwaltung von Windows können festlegen, die [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Zeiger auf `null` Wenn die Methode keine in-Parameter hat.

In `ppInSignature` und `ppOutSignature` beschreiben "" in und out-Parameter, jeweils als Eigenschaften in einem `IWbemClassObject` Instanz der Systemklasse [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx). Die Eigenschaften im `ppInsignature` heißen **Param***n*, wobei  *n*  ist die Position des Parameters in der Methodensignatur (z. B. als `Param1`, `Param2`usw..). Die Eigenschaften im `ppOutSignature` sind auch mit dem Namen **Param***n*, und der Rückgabewert lautet **ReturnValue**. Weitere Informationen und ein Beispiel finden Sie unter [IWbemClassObject::GetMethod Methode](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).

## <a name="requirements"></a>Anforderungen  
**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
