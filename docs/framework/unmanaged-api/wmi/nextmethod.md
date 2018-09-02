---
title: NextMethod-Funktion (Referenz zur nicht verwalteten API)
description: Die NextMethod-Funktion ruft die nächste Methode in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d019c67849197cd24171ff607e60e9f08d5ff70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43451622"
---
# <a name="nextmethod-function"></a>NextMethod-Funktion
Ruft die nächste Methode in einer Enumeration, die mit einem Aufruf von beginnt [BeginMethodEnumeration](beginmethodenumeration.md).  

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
[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.

`lFlags`  
[in] Reserviert. Dieser Parameter muss 0 sein.

`pName`  
[out] Ein Zeiger, der auf zeigt `null` vor dem Aufruf. Wenn die Funktion zurückgibt, die Adresse eines neuen `BSTR` , enthält der Name der Methode. 

`ppSignatureIn`  
[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , enthält die `in` Parameter für die Methode. 

`ppSignatureOut`  
[out] Ein Zeiger, der einen Zeiger auf empfängt eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) , enthält die `out` Parameter für die Methode. 

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Es gibt keine weiteren Eigenschaften in der Enumeration. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) Methode.

Der Aufrufer beginnt der Enumerationssequenz durch Aufrufen der [BeginMethodEnumeration](beginmethodenumeration.md) funktionieren, und klicken Sie dann die [NextMethod]-Funktion aufruft, bis die Funktion gibt `WBEM_S_NO_MORE_DATA`. Der Aufrufer wird optional die Sequenz beendet, indem Aufrufen [EndMethodEnumeration](endmethodenumeration.md). Der Aufrufer kann die Enumeration beenden, in der frühen durch Aufrufen von [EndMethodEnumeration](endmethodenumeration.md) zu einem beliebigen Zeitpunkt.

## <a name="example"></a>Beispiel

Eine C++-Beispiel finden Sie unter den [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
