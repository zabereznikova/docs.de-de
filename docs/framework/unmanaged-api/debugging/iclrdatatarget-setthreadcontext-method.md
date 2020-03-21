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
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179126"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext-Methode
Legt den aktuellen Kontext des angegebenen Threads im Zielprozess fest. Diese Methode wird von den ClR-Datenzugriffsdiensten (Common Language Runtime) aufgerufen.  
  
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
 [in] Der Betriebssystembezeichner eines Threads im Zielprozess.  
  
 `contextSize`  
 [in] Die Größe des Kontexts.  
  
 `context`  
 [in] Zeiger auf einen Puffer, der den Kontext enthält.  
  
 Die Daten `context` im Puffer werden im Format der `CONTEXT` Win32-Struktur vorliegen. Der Kontext gibt prozessorspezifische Registerdaten an, sodass `CONTEXT` die Definition der Win32-Struktur von der Architektur des Prozessors abhängt. Die Definition der Win32-Struktur `CONTEXT` finden Sie in der WinNT.h-Headerdatei.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
