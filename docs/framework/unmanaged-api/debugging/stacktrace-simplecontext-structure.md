---
title: StackTrace_SimpleContext-Struktur
ms.date: 03/30/2017
api_name:
- StackTrace_SimpleContext
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SimpleContext
helpviewer_keywords:
- SimpleContext structure [.NET Framework debugging]
- StackTrace_SimpleContext structure [.NET Framework debugging]
ms.assetid: d4cef11f-a8ca-49bc-a1b8-6631f9e28f3e
topic_type:
- apiref
ms.openlocfilehash: 1cd3c34fc292e4a050fa8a75078283e34425fc8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139128"
---
# <a name="stacktrace_simplecontext-structure"></a>StackTrace_SimpleContext-Struktur
Stellt einen einfachen Kontext bereit, der statt einer vollständigen `CONTEXT`-Struktur verwendet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`StackOffset`|Der Stapelzeiger oder der Eingabe Stapelzeiger (ESP) auf x86-Plattformen.|  
|`FrameOffset`|Der Frame Offset oder das EBP-Register auf x86-Plattformen.|  
|`InstructionOffset`|Der Anweisungs Zeiger oder der Eingabe Anweisungs Zeiger (EIP) auf x86-Plattformen.|  
  
## <a name="remarks"></a>Hinweise  
 Da Stapel Überwachungsfunktionen in der Regel nur die Adresse, den Frame Offset und die Stapel Adresse zurückgeben müssen, können Sie optional die `SimpleContext` Struktur anstelle einer großen `CONTEXT` Struktur verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace. h  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
