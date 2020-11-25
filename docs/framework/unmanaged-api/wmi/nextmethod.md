---
title: Nextmethod-Funktion (Referenz zur nicht verwalteten API)
description: Die nextmethod-Funktion Ruft die nächste Methode in einer Enumeration ab.
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
ms.openlocfilehash: a0466aee47b0a6142870640c78b43f49e221ac2b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726768"
---
# <a name="nextmethod-function"></a>NextMethod-Funktion

Ruft die nächste Methode in einer Enumeration ab, die mit einem Aufrufen von [beginmethodenumeration](beginmethodenumeration.md)beginnt.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`pName`  
vorgenommen Ein Zeiger, der vor dem-Befehl auf verweist `null` . Wenn die Funktion zurückgegeben wird, die Adresse eines neuen `BSTR` , der den Methodennamen enthält.

`ppSignatureIn`  
vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `in` Parameter für die Methode enthält.

`ppSignatureOut`  
vorgenommen Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `out` Parameter für die Methode enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Die Funktion wurde nicht aufgerufen [`BeginEnumeration`](beginenumeration.md) . |
| `WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | In der-Enumeration sind keine weiteren Eigenschaften vorhanden. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.

Der Aufrufer beginnt die enumerationssequenz, indem er die [beginmethodenumeration](beginmethodenumeration.md) -Funktion aufruft, und ruft dann die Funktion [nextmethod] auf, bis die Funktion zurückgibt `WBEM_S_NO_MORE_DATA` . Optional schließt der Aufrufer die Sequenz durch Aufrufen von [endmethodenumeration](endmethodenumeration.md)ab. Der Aufrufer kann die Enumeration frühzeitig beenden, indem [endmethodenumeration](endmethodenumeration.md) jederzeit aufgerufen wird.

## <a name="example"></a>Beispiel

Ein C++-Beispiel finden Sie unter der [IWbemClassObject:: nextmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) -Methode.

## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
