---
title: GetCurrentApartmentType-Funktion (Nicht verwaltete API-Referenz)
description: Die GetCurrentApartmentType-Funktion ruft den Apartmenttyp ab, in dem der Aufrufer ausgeführt wird.
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176824"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType-Funktion
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
[in] Dieser Parameter ist nicht verwendet.

`ptr`  
[in] Ein Zeiger auf eine [IComThreadingInfo-Instanz.](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)

`aptType`  
[out] Ein Zeiger auf einen APTTYPE-Enumerationswert, der die Wohnung des Aufrufers angibt. [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype)

## <a name="return-value"></a>Rückgabewert

|Dauerhaft  |value  |Beschreibung  |
|---------|---------|---------|
| `S_OK` | 0 | Die Funktion wurde erfolgreich abgeschlossen. |
| `E_FAIL` | 0x80000008 | Der Anrufer wird nicht in einer Wohnung ausgeführt. |
  
## <a name="remarks"></a>Bemerkungen

Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType-Methode.](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)

## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
