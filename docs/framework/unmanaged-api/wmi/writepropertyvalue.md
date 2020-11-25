---
title: Funktion "Beschreib tepropertyvalue" (Referenz zur nicht verwalteten API)
description: Die Funktion "schreitepropertyvalue" schreibt Bytes in eine Eigenschaft.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e225516b06c477dc1a24cf721bc3e1ade9076b75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729407"
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue-Funktion

Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Instanz.

`lHandle`  
in Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert. Das Handle kann durch Aufrufen der [getpropertyhandle](getpropertyhandle.md) -Funktion abgerufen werden.

`lNumBytes`  
in Die Anzahl der Bytes, die in die Eigenschaft geschrieben werden. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".

`pHandle` vorgenommen Ein Zeiger auf das Bytearray, das die Daten enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:

|Konstante  |Wert  |BESCHREIBUNG  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 beim | Es ist ein Typenkonflikt aufgetreten. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktions Aufrufvorgang war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen aufzurufenden Befehl an die [IWbemClassObject:: Write-PropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) -Methode.

Verwenden Sie diese Funktion, um die Zeichenfolge und alle anderen nicht- `DWORD` oder nicht-Daten festzulegen `QWORD` .

Für nicht-Zeichen folgen-Eigenschaftswerte `lNumBytes` muss die richtige Datengröße des angegebenen Eigenschaftentyps sein. Für Zeichen folgen Eigenschaftswerte `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes sein, und die Zeichenfolge selbst muss eine gerade Länge in Bytes aufweisen und mit einem NULL-Terminierungs Zeichen befolgt werden.

## <a name="requirements"></a>Requirements (Anforderungen)  

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
