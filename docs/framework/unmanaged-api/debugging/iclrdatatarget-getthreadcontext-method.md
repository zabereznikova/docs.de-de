---
title: ICLRDataTarget::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179179"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext-Methode
Ruft den aktuellen Ausführungskontext für den angegebenen Thread im Zielprozess ab. Diese Methode wird von den Common Language Runtime-Datenzugriffsdiensten aufgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Der Betriebssystembezeichner eines Threads im Zielprozess.  
  
 `contextFlags`  
 [in] Flags, die angeben, welche Teile des Kontexts zurückgegeben werden sollen. Die Implementierung gibt zumindest diese Teile des Kontexts zurück.  
  
 `contextSize`  
 [in] Die Größe des Kontexts.  
  
 `context`  
 [out] Zeiger auf einen Puffer, in dem der Kontext platziert werden soll.  
  
 Die Daten `context` im Puffer müssen im Format der `CONTEXT` Win32-Struktur vorliegen. Der Kontext gibt prozessorspezifische Registerdaten an, sodass `CONTEXT` die Definition der Win32-Struktur von der Architektur des Prozessors abhängt. Die Definition der Win32-Struktur `CONTEXT` finden Sie in der WinNT.h-Headerdatei.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
