---
title: PutMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die PutMethod-Funktion erstellt eine Methode an.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutMethod
helpviewer_keywords: PutMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a>PutMethod-Funktion
Erstellt eine Methode an.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.

`wszName`  
[in] Der Name der Methode zu erstellen. 

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pSignatureIn`  
[in] Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , enthält die `in` Parameter für die Methode. Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.  

`pSignatureOut`  
[in]  Ein Zeiger auf eine Kopie der [__Parameters Systemklasse](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , enthält die `out` Parameter für die Methode. Dieser Parameter wird ignoriert, wenn auf festgelegt `null`.
 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Einen oder mehrere Parameter sind ungültig. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | Die `[in, out]` Methodenparameter, die in beiden angegebenen der *pInSignature* und *pOutSignature* Objekte verfügen über unterschiedliche Qualifizierer.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Ein Methodenparameter fehlt die Angabe von der **ID** Qualifizierer. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Die ID-Reihe, die das die Methodenparameter zugewiesen ist, ist nicht aufeinander folgende oder beginnt nicht mit 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Der Rückgabewert für eine Methode verfügt über eine **ID** Qualifizierer. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Es wurde versucht, den Methodennamen einer vorhandenen aus einer übergeordneten Klasse wiederverwenden, und die Signaturen stimmte nicht überein. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) Methode.

Dieser Methodenaufruf wird nur unterstützt, wenn `ptr` ist die Definition einer CIM-Klasse. Methode Manipulation steht nicht zur Verfügung [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) Zeiger, die auf das CIM-Instanzen verweisen.

Benutzer können keine Methoden mit Namen erstellen, die mit einem Unterstrich beginnen oder enden. Dies ist für Systemklassen und Eigenschaften reserviert.

Für eine Methode die `in` und `out` Parameter werden als Eigenschaften in beschrieben [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) Objekte.

Ein `[in/out]` Parameter kann definiert werden, indem Sie die gleiche Eigenschaft an beide Objekte verweist, zu der `pInSignature` und `pOutSignature` Parameter. In diesem Fall die Eigenschaften verwenden dieselbe **ID** Qualifiziererwert.

Jede Eigenschaft in ein [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) Objekt außer-Klasse `ReturnValue` benötigen eine **ID** Qualifizierer, ein nullbasierter numerischen Wert, der die Reihenfolge angibt, in der die Parameter angezeigt werden. Können keine zwei Parameter verfügen über denselben **ID** Wert und keine **ID** Wert kann übersprungen werden. Wenn eine der Bedingungen auftritt, die `PutMethod` -Funktion zurückgegeben `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Beispiel

Ein Beispiel finden Sie die [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
