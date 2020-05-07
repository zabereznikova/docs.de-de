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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860605"
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
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.  
  
 `contextFlags`  
 in Flags, die angeben, welche Teile des Kontexts zurückgegeben werden sollen. Die-Implementierung gibt mindestens diese Teile des Kontexts zurück.  
  
 `contextSize`  
 in Die Größe des Kontexts.  
  
 `context`  
 vorgenommen Zeiger auf einen Puffer, in den der Kontext platziert werden soll.  
  
 Die Daten im `context` Puffer müssen das Format der Win32 `CONTEXT` -Struktur aufweisen. Der Kontext gibt prozessorspezifische Register Daten an, sodass die Definition der Win32 `CONTEXT` -Struktur von der Architektur des Prozessors abhängig ist. Die Definition der Win32 `CONTEXT` -Struktur finden Sie in der Header Datei "Winnt. h".  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
