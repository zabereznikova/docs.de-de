---
title: ICLRDataTarget::GetTLSValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab3d978e9500a17f5b8ae011322ad05aedddf98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a>ICLRDataTarget::GetTLSValue-Methode
Ruft einen Wert aus dem lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess. Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.  
  
 `index`  
 [in] Der Index der Position. Dieser Wert muss ein gültiger Index in den lokalen Speicher des angegebenen Threads.  
  
 `value`  
 [out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der den Wert angibt, aus dem angegebenen TLS-Speicherort zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
