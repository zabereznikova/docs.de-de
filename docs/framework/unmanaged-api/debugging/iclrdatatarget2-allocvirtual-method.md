---
title: ICLRDataTarget2::AllocVirtual-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ba9200419d6b6fef467ae02bd74101414e125da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698004"
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual-Methode
Wird aufgerufen, durch die common Language Runtime (CLR) Datenzugriffsdiensten der Speicher im Adressraum dieses Prozesses Ziel reserviert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `addr`  
 [in] Ein `CLRDATA_ADDRESS` Wert, der angibt, der die angeforderte Startadresse des Arbeitsspeichers, die zugeordnet werden.  
  
 `size`  
 [in] Die Größe in Bytes, des Arbeitsspeichers, die zugeordnet werden.  
  
 `typeFlags`  
 [in] Flags, die die Zuordnung von Arbeitsspeicher zu steuern. Finden Sie unter Win32 `VirtualAlloc` Funktion.  
  
 `protectFlags`  
 [in] Die Schutzattribute für den zugeordneten Speicher. Finden Sie unter Win32 `VirtualAlloc` Funktion.  
  
 `virt`  
 [out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der die eigentliche Startadresse des zugeordneten Speichers angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `AllocVirtual` Methode dient als ein logischer Wrapper für die Win32- `VirtualAlloc` Funktion.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [FreeVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
