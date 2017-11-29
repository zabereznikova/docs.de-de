---
title: ICLRDataTarget2::AllocVirtual-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b27ae7dcda8cc5e14d9c0f72f74c8bda13169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a>ICLRDataTarget2::AllocVirtual-Methode
Wird von der common Language Runtime (CLR) Datenzugriffsdiensten der belegen von Speicher im Adressraum dieses Zielprozesses aufgerufen.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `addr`  
 [in] Ein `CLRDATA_ADDRESS` Wert, der angibt, die angeforderte Startadresse des Arbeitsspeichers zugeordnet werden soll.  
  
 `size`  
 [in] Die Größe in Bytes, des Arbeitsspeichers zugeordnet werden soll.  
  
 `typeFlags`  
 [in] Flags, die die Belegung von Speicher zu steuern. Finden Sie unter Win32 `VirtualAlloc` Funktion.  
  
 `protectFlags`  
 [in] Die Schutzattribute für den reservierten Arbeitsspeicher. Finden Sie unter Win32 `VirtualAlloc` Funktion.  
  
 `virt`  
 [out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der die eigentliche Startadresse des belegten angibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `AllocVirtual` Methode dient als logischer Wrapper für die Win32- `VirtualAlloc` Funktion.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataTarget2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [FreeVirtual-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
