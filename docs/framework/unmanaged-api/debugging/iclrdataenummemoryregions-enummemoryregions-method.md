---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1685b1f739519485e5e68928b29a874587e6f9c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode
Listet die angegebenen Bereiche des Arbeitsspeichers.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `callback`  
 [in] Ein Zeiger auf ein [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) Instanz, die von dieser Methode für jede Speicherbereich aufgezählt werden, um den Debugger des Ergebnisses benachrichtigen aufgerufen wird.  
  
 Die Enumeration von Speicherbereiche wird fortgesetzt, selbst wenn der Rückruf ein Fehler weist darauf hin.  
  
 `miniDumpFlags`  
 [in] Nicht verwendet.  
  
 `clrFlags`  
 [in] Der Wert der [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) Enumeration, der angibt, die Bereiche des Arbeitsspeichers aufgelistet werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode verwendet den angegebenen [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) Instanz an den Aufrufer der Ergebnisse zu benachrichtigen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataEnumMemoryRegions-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
