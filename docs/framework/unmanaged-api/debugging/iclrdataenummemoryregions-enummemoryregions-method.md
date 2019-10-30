---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: 693ec07176f80711709cd9b85c6886bea8be74b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122966"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions-Methode
Listet angegebene Speicherbereiche auf.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `callback`  
 in Ein Zeiger auf eine [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) -Instanz, die von dieser Methode für jeden aufgezählten Speicherbereich aufgerufen wird, um den Debugger über das Ergebnis zu benachrichtigen.  
  
 Die Enumeration der Speicherbereiche wird auch dann fortgesetzt, wenn der Rückruf auf einen Fehler hinweist.  
  
 `miniDumpFlags`  
 in Nicht verwendet.  
  
 `clrFlags`  
 in Ein Wert der [CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md) -Enumeration, der die aufzuzählenden Speicherbereiche angibt.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode verwendet die angegebene [ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md) -Instanz, um den Aufrufer über Ergebnisse zu benachrichtigen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataEnumMemoryRegions-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)
