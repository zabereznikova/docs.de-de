---
title: Getcurrentapartmenttype-Funktion (Referenz zur nicht verwalteten API)
description: Die getcurrentapartmenttype-Funktion Ruft den Typ des Apartment ab, in dem der Aufrufer ausgeführt wird.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ecd2b49d6850a8fae25ddca54f855fdda2ccabb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120351"
---
# <a name="getcurrentapartmenttype-function"></a>Getcurrentapartmenttype-Funktion
Ruft den Typ des Apartments ab, in dem die aufrufende Funktion ausgeführt wird.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
in Dieser Parameter wird nicht verwendet.

`ptr`  
in Ein Zeiger auf eine [icomthreadinginfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) -Instanz.

`aptType`  
vorgenommen Ein Zeiger auf einen [apttype](/windows/win32/api/objidlbase/ne-objidlbase-apttype) -Enumerationswert, der das Apartment des Aufrufers angibt.

## <a name="return-value"></a>Rückgabewert

|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `S_OK` | 0 | Die Funktion wurde erfolgreich abgeschlossen. |
| `E_FAIL` | 0x80000008 | Der Aufrufer wird nicht in einem Apartment ausgeführt. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufrufen der [icomthreadinginfo:: getcurrentapartmenttype](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) -Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils. idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
