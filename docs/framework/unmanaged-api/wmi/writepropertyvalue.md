---
title: WritePropertyValue-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion WritePropertyValue schreibt Bytes auf eine Eigenschaft an.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: WritePropertyValue
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: WritePropertyValue
helpviewer_keywords: WritePropertyValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26337a13ab9840b79c253d4af2d84a10e70877c5
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue-Funktion
Schreibt eine angegebene Anzahl von Bytes an eine Eigenschaft, die durch ein Eigenschaftshandle identifiziert.

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
[in] Ein Zeiger auf ein [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Instanz.

`lHandle`  
[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft kennzeichnet. Das Handle abgerufen werden kann, durch Aufrufen der [GetPropertyHandle](getpropertyhandle.md) Funktion.   

`lNumBytes`  
[in] Die Anzahl der Bytes, die der Eigenschaft geschrieben wird. Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.

`pHandle`   
[out] Ein Zeiger auf das Bytearray, das Daten enthält.

## <a name="return-value"></a>Rückgabewert

Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Ein Parameter ist ungültig. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | Ein Typenkonflikt aufgetreten ist. |
|`WBEM_S_NO_ERROR` | 0 | Der Funktionsaufruf war erfolgreich.  |
  
## <a name="remarks"></a>Hinweise

Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) Methode.

Mit dieser Funktion können Sie die Zeichenfolge "und" alle anderen nicht - festgelegt`DWORD` oder nicht-`QWORD` Daten.

Für Eigenschaftswerte Objektressourcen `lNumBytes` müssen die richtigen Datengröße des Eigenschaftentyps angegeben werden. Für Zeichenfolge-Eigenschaftswerte `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes und die Zeichenfolge selbst muss eine Länge in Bytes, und mit einem Null-Abschlusszeichen folgen.

## <a name="requirements"></a>Anforderungen  
**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
