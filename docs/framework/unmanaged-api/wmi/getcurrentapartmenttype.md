---
title: GetCurrentApartmentType-Funktion (Referenz zur nicht verwalteten API)
description: Die GetCurrentApartmentType-Funktion ruft ab, der Typ des Apartment, in dem der Aufrufer ausgeführt wird.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de85eb310de70dc8fd61f7c06abca95ec267f87
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42931414"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType-Funktion
Ruft den Typ des Apartment, in dem der Aufrufer ausgeführt wird.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Parameter

`vFunc`  
[in] Dieser Parameter wird nicht verwendet.

`ptr`  
[in] Ein Zeiger auf ein [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) Instanz.

`aptType`  
[out] Ein Zeiger auf ein [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) Enumerationswert, der Aufrufer Apartment angibt.

## <a name="return-value"></a>Rückgabewert


|Konstante  |Wert  |Beschreibung  |
|---------|---------|---------|
| `S_OK` | 0 | Die Funktion wurde erfolgreich abgeschlossen. |
| `E_FAIL` | 0x80000008 | Der Aufrufer eine Wohnung nicht ausgeführt. |
  
## <a name="remarks"></a>Hinweise

Diese Funktion umschließt einen Aufruf der [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) Methode.

## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** WMINet_Utils.idl  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Siehe auch  
[WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)](index.md)
