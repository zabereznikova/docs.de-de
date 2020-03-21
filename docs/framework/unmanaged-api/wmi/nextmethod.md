---
title: NextMethod-Funktion (Nicht verwaltete API-Referenz)
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
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174926"
---
# <a name="nextmethod-function"></a>NextMethod-Funktion
Ruft die nächste Methode in einer Enumeration ab, die mit einem Aufruf von [BeginMethodEnumeration](beginmethodenumeration.md)beginnt.  

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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in]: Reserviert Dieser Parameter muss 0 sein.

`pName`  
[out] Ein Zeiger, auf `null` den vor dem Aufruf zeigt. Wenn die Funktion zurückkehrt, wird `BSTR` die Adresse eines Neuen, der den Methodennamen enthält.

`ppSignatureIn`  
[out] Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `in` Parameter für die Methode enthält.

`ppSignatureOut`  
[out] Ein Zeiger, der einen Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) empfängt, das die `out` Parameter für die Methode enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | Es gab keinen [`BeginEnumeration`](beginenumeration.md) Aufruf der Funktion. |
| `WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Es sind keine Eigenschaften mehr in der Enumeration vorhanden. |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::NextMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)

Der Aufrufer beginnt die Enumerationssequenz, indem er die [BeginMethodEnumeration-Funktion](beginmethodenumeration.md) aufruft, `WBEM_S_NO_MORE_DATA`und ruft dann die [NextMethod]-Funktion auf, bis die Funktion zurückgibt. Optional beendet der Aufrufer die Sequenz, indem er [EndMethodEnumeration aufruft.](endmethodenumeration.md) Der Aufrufer kann die Enumeration jederzeit vorzeitig beenden, indem er [EndMethodEnumeration](endmethodenumeration.md) aufruft.

## <a name="example"></a>Beispiel

Ein C++-Beispiel finden Sie in der [IWbemClassObject::NextMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
