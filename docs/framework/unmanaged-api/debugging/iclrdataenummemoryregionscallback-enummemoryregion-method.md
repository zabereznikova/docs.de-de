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
ms.openlocfilehash: b5ca524d223fad7ded0d56def3293eb40be69fa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703719"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode

Wird von [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) aufgerufen, um dem Debugger das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten, zu melden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 in Die Startadresse des Speicherbereichs, der aufgelistet werden soll.  
  
 `size`  
 in Die Größe des Arbeitsspeicher Bereichs in Bytes.  
  
## <a name="remarks"></a>Hinweise  

 Die- `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode ruft diese Rückruf Methode nach jedem Versuch auf, einen Speicherbereich aufzulisten. Die Enumeration wird auch dann fortgesetzt, wenn diese Methode ein HRESULT zurückgibt, das einen Fehler angibt.  
  
 Die von diesem Rückruf gemeldeten Regionen können Duplikate oder überlappende Bereiche sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](iclrdataenummemoryregionscallback-interface.md)
