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
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723700"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext-Methode

Legt den aktuellen Kontext des angegebenen Threads im Ziel Prozess fest. Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.  
  
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
 in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.  
  
 `contextSize`  
 in Die Größe des Kontexts.  
  
 `context`  
 in Zeiger auf einen Puffer, der den Kontext enthält.  
  
 Die Daten im `context` Puffer werden im Format der Win32- `CONTEXT` Struktur angezeigt. Der Kontext gibt prozessorspezifische Register Daten an, sodass die Definition der Win32 `CONTEXT` -Struktur von der Architektur des Prozessors abhängig ist. Die Definition der Win32-Struktur finden Sie in der Header Datei "Winnt. h" `CONTEXT` .  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
