---
title: ICLRDataTarget::GetThreadContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480b65b279dbc0359b078f3f1d543f63a0bfd0f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext-Methode
Ruft den aktuellen Ausführungskontext für den angegebenen Thread im Zielprozess. Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.  
  
 `contextFlags`  
 [in] Flags, die angeben, welche Teile des Kontexts zurück. Die Implementierung gibt mindestens diese Teile des Kontexts zurück.  
  
 `contextSize`  
 [in] Die Größe des Kontexts.  
  
 `context`  
 [out] Ein Zeiger auf einen Puffer, in dem den Kontext platziert.  
  
 Die Daten in der `context` Puffer muss im Format der Win32- `CONTEXT` Struktur. Der Kontext gibt prozessorspezifische Registerdaten an, also die Definition der Win32- `CONTEXT` Struktur hängt von der Prozessorarchitektur. Finden Sie in der Headerdatei "Winnt.h" für die Definition der Win32- `CONTEXT` Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
