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
ms.openlocfilehash: b5f6a830cbe601443f03cd91a356c7e49450e7f3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793731"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext-Methode
Ruft den aktuellen Ausführungs Kontext für den angegebenen Thread im Ziel Prozess ab. Diese Methode wird vom Common Language Runtime Data Access Services aufgerufen.  
  
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
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.  
  
 `contextFlags`  
 in Flags, die angeben, welche Teile des Kontexts zurückgegeben werden sollen. Die-Implementierung gibt mindestens diese Teile des Kontexts zurück.  
  
 `contextSize`  
 in Die Größe des Kontexts.  
  
 `context`  
 vorgenommen Zeiger auf einen Puffer, in den der Kontext platziert werden soll.  
  
 Die Daten im `context` Puffer müssen das Format der Win32-`CONTEXT` Struktur aufweisen. Der Kontext gibt prozessorspezifische Register Daten an, sodass die Definition der Win32-`CONTEXT` Struktur von der Architektur des Prozessors abhängig ist. Die Definition der Win32-`CONTEXT` Struktur finden Sie in der Header Datei "Winnt. h".  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
