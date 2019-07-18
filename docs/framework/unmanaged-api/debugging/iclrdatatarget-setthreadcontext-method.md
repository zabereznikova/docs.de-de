---
title: ICLRDataTarget::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: edd70dd4cfc2e26b30ee0deec79b7d126d1f76a1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738584"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext-Methode
Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest. Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]   
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.  
  
 `contextSize`  
 [in] Die Größe des Kontexts.  
  
 `context`  
 [in] Zeiger auf einen Puffer, der den Kontext enthält.  
  
 Die Daten in die `context` Puffer werden im Format von Win32 `CONTEXT` Struktur. Den Kontext angibt, macht prozessorspezifische Registerdaten, also die Definition von Win32 `CONTEXT` Struktur hängt von der Prozessorarchitektur. Finden Sie in der Headerdatei "WinNT.h" für die Definition von Win32 `CONTEXT` Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
