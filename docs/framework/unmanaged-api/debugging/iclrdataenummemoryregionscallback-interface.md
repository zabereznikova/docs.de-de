---
title: ICLRDataEnumMemoryRegionsCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860665"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a>ICLRDataEnumMemoryRegionsCallback-Schnittstelle
Stellt eine Rückruf Methode für [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) bereit, um dem Debugger das Ergebnis eines Versuchs zum Auflisten eines bestimmten Speicherbereichs zu melden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[EnumMemoryRegion-Methode](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|Wird von `ICLRDataEnumMemoryRegions::EnumMemoryRegions` aufgerufen, um dem Debugger das Ergebnis eines Versuchs, einen angegebenen Bereich des Speichers aufzulisten, zu melden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [Debugschnittstellen](debugging-interfaces.md)
