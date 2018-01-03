---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a284d7277aa2f8c474ca4aab3dd6208bc3b2bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
Wird aufgerufen, indem [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) auf das Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten, die im Debugger zu melden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Die Startadresse des Arbeitsspeicherbereichs, der aufgelistet werden soll.  
  
 `size`  
 [in] Die Größe des Arbeitsspeicherbereichs in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode ruft diese Rückrufmethode nach jedem Versuch, einen Arbeitsspeicherbereich aufzulisten. Die Enumeration wird fortgesetzt, auch wenn diese Methode gibt einen HRESULT-Fehler zurück.  
  
 Bereiche, die von diesem Rückruf gemeldeten möglicherweise Duplikate oder überlappende Bereiche.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
