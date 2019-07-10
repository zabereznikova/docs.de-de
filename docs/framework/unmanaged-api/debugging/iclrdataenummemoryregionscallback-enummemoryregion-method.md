---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5c03b7010418f75aff984102d7fa4fb089c4d59
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738821"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
Wird aufgerufen, indem [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Die Startadresse des Arbeitsspeicherbereichs, die aufgelistet werden soll.  
  
 `size`  
 [in] Die Größe des Arbeitsspeicherbereichs in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode wird diese Callback-Methode aufrufen, nach jedem Versuch, einen Speicher aufzulisten. Die Enumeration wird fortgesetzt, selbst wenn diese Methode einen HRESULT-Fehler zurückgegeben.  
  
 Regionen, die von diesem Rückruf gemeldeten können es sich um Duplikate oder überlappende Bereiche sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
