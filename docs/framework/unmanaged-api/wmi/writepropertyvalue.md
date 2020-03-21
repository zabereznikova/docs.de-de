---
title: WritePropertyValue-Funktion (Nicht verwaltete API-Referenz)
description: Die WritePropertyValue-Funktion schreibt Bytes in eine Eigenschaft.
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174835"
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IWbemObjectAccess-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)

`lHandle`  
[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert. Das Handle kann abgerufen werden, indem die [GetPropertyHandle-Funktion](getpropertyhandle.md) aufgerufen wird.

`lNumBytes`  
[in] Die Anzahl der Bytes, die in die Eigenschaft geschrieben werden. Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)

`pHandle`[out] Ein Zeiger auf das Bytearray, das die Daten enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist nicht gültig. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Es ist ein Typenkonflikt aufgetreten. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::WritePropertyValue-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)

Verwenden Sie diese Funktion, um`DWORD` Zeichenfolgen`QWORD` und alle anderen Nicht- oder Nicht-Daten festzulegen.

Bei Nicht-Zeichenfolgen-Eigenschaftswerten `lNumBytes` muss die richtige Datengröße des angegebenen Eigenschaftstyps angegeben sein. Für Zeichenfolgeneigenschaftswerte `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes sein, und die Zeichenfolge selbst muss eine gerade Länge in Bytes haben und mit einem Null-Beendigungszeichen gefolgt werden.

## <a name="requirements"></a>Requirements (Anforderungen)  
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
