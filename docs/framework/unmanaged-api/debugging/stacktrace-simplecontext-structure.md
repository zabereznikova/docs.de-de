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
ms.openlocfilehash: c81a5787eb06971e3d52aff5d1c1154a72564daf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790333"
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
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** SOS_Stacktrace. h  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Strukturen](debugging-structures.md)
- [Debuggen](index.md)
