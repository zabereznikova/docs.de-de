---
title: _EFN_GetManagedObjectName-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectName
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectName
helpviewer_keywords: _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80e36f6c60c4c305cad9176cd7f185d8b6d2fdf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectname-function"></a>_EFN_GetManagedObjectName-Funktion
Ruft den Namen des Typs mithilfe der bereitgestellten verwalteten Objektzeiger ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `Client`  
 [in] Ein Zeiger auf den Client Debuggen.  
  
 `objAddr`  
 [in] Ein Zeiger des verwalteten Objekts.  
  
 szName  
 [out] Der Name des Typs.  
  
 `cbName`  
 [out] Die Anzahl der Zeichen im Zeichenfolgenpuffer verfügbar.  
  
## <a name="remarks"></a>Hinweise  
 Es ist kein verwalteter Code auf dem Thread derzeit im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und dem Fehlercode 0 x 1000 zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace.h  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
