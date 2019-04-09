---
title: WritePropertyValue-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion WritePropertyValue schreibt Bytes in eine Eigenschaft an.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98103367f497b18f9b8fbd61a37abf9816b8356
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107938"
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue-Funktion
Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Syntax  
  
```  
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
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.

`lHandle`  
[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert. Das Handle abgerufen werden kann, durch den Aufruf der [GetPropertyHandle](getpropertyhandle.md) Funktion.   

`lNumBytes`  
[in] Die Anzahl der Bytes, die auf die Eigenschaft geschrieben werden. Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`pHandle`   
[out] Ein Zeiger auf das Bytearray, das Daten enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Es ist ein Typenkonflikt aufgetreten. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) Methode.

Mit dieser Funktion können Sie die Zeichenfolge "und" alle anderen nicht - festgelegt`DWORD` oder nicht-`QWORD` Daten.

Keine Zeichenfolge darstellen Eigenschaftswerte `lNumBytes` müssen die richtigen Datengröße des Eigenschaftentyps angegeben werden. Für Zeichenfolgen-Eigenschaftswerten `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes und die Zeichenfolge selbst muss ein sogar Länge in Bytes und eine Null-Terminierungszeichen folgen.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
