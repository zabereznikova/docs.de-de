---
title: CorDebugRegister-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
ms.openlocfilehash: 85df98e83396c9439c28dd41a3ffa02b820c9c3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726053"
---
# <a name="cordebugregister-enumeration"></a>CorDebugRegister-Enumeration

Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|Ein Anweisungszeigerregister für einen beliebigen Prozessor.|  
|`REGISTER_STACK_POINTER`|Ein Stapelzeigerregister für einen beliebigen Prozessor.|  
|`REGISTER_FRAME_POINTER`|Ein Framezeigerregister für einen beliebigen Prozessor.|  
|`REGISTER_X86_EIP`|Das Anweisungszeigerregister für den x86-Prozessor.|  
|`REGISTER_X86_ESP`|Das Stapelzeigerregister für den x86-Prozessor.|  
|`REGISTER_X86_EBP`|Das Basiszeigerregister für den x86-Prozessor.|  
|`REGISTER_X86_EAX`|Das A-Datenregister für den x86-Prozessor.|  
|`REGISTER_X86_ECX`|Das C-Datenregister für den x86-Prozessor.|  
|`REGISTER_X86_EDX`|Das D-Datenregister für den x86-Prozessor.|  
|`REGISTER_X86_EBX`|Das B-Datenregister für den x86-Prozessor.|  
|`REGISTER_X86_ESI`|Das Quellindexregister für den x86-Prozessor.|  
|`REGISTER_X86_EDI`|Das Zielindexregister für den x86-Prozessor.|  
|`REGISTER_X86_FPSTACK_0`|Das Stapelregister 0 im x86-Gleitkommaprozessor (FP).|  
|`REGISTER_X86_FPSTACK_1`|Das Stapelregister 1 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_2`|Das Stapelregister 2 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_3`|Das Stapelregister 3 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_4`|Das Stapelregister 4 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_5`|Das Stapelregister 5 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_6`|Das Stapelregister 6 für den x86-FP-Prozessor.|  
|`REGISTER_X86_FPSTACK_7`|Das Stapelregister 7 für den x86-FP-Prozessor.|  
|`REGISTER_AMD64_RIP`|Das Anweisungszeigerregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RSP`|Das Stapelzeigerregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RBP`|Das Basiszeigerregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RAX`|Das A-Datenregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RCX`|Das C-Datenregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RDX`|Das D-Datenregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RBX`|Das B-Datenregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RSI`|Das Quellindexregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_RDI`|Das Zielindexregister für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R8`|Das Datenregister 8 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R9`|Das Datenregister 9 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R10`|Das Datenregister 10 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R11`|Das Datenregister 11 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R12`|Das Datenregister 12 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R13`|Das Datenregister 13 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R14`|Das Datenregister 14 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_R15`|Das Datenregister 15 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM0`|Das Multimediaregister 0 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM1`|Das Multimediaregister 1 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM2`|Das Multimediaregister 2 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM3`|Das Multimediaregister 3 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM4`|Das Multimediaregister 4 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM5`|Das Multimediaregister 5 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM6`|Das Multimediaregister 6 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM7`|Das Multimediaregister 7 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM8`|Das Multimediaregister 8 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM9`|Das Multimediaregister 9 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM10`|Das Multimediaregister 10 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM11`|Das Multimediaregister 11 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM12`|Das Multimediaregister 12 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM13`|Das Multimediaregister 13 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM14`|Das Multimediaregister 14 für den AMD64-Prozessor.|  
|`REGISTER_AMD64_XMM15`|Das Multimediaregister 15 für den AMD64-Prozessor.|  
|`REGISTER_IA64_BSP`|Das Stapelzeigerregister für den IA-64-Prozessor.|  
|`REGISTER_IA64_R0`|Das Datenregister 0 für den IA-64-Prozessor.|  
|`REGISTER_IA64_F0`|Das FP-Datenregister 0 für den IA-64-Prozessor.|  
|`REGISTER_ARM_PC`|Das Programmzählerregister (R15) für den ARM-Prozessor.|  
|`REGISTER_ARM_SP`|Das Stapelzeigerregister (R13) für den ARM-Prozessor.|  
|`REGISTER_ARM_R0`|Das Datenregister R0 für den ARM-Prozessor.|  
|`REGISTER_ARM_R1`|Das Datenregister R1 für den ARM-Prozessor.|  
|`REGISTER_ARM_R2`|Das Datenregister R2 für den ARM-Prozessor.|  
|`REGISTER_ARM_R3`|Das Datenregister R3 für den ARM-Prozessor.|  
|`REGISTER_ARM_R4`|Register R4 für den ARM-Prozessor.|  
|`REGISTER_ARM_R5`|Register R5 für den ARM-Prozessor.|  
|`REGISTER_ARM_R6`|Register R6 für den ARM-Prozessor.|  
|`REGISTER_ARM_R7`|Register R7 (der THUMB-Framezeiger) für den ARM-Prozessor.|  
|`REGISTER_ARM_R8`|Register R8 für den ARM-Prozessor.|  
|`REGISTER_ARM_R9`|Register R9 für den ARM-Prozessor.|  
|`REGISTER_ARM_R10`|Register R10 für den ARM-Prozessor.|  
|`REGISTER_ARM_R11`|Der Framezeiger für den ARM-Prozessor.|  
|`REGISTER_ARM_R12`|Register R12 für den ARM-Prozessor.|  
|`REGISTER_ARM_LR`|Das Link-Register (R14) für den ARM-Prozessor.|  
  
## <a name="remarks"></a>Hinweise  

 Es gibt 128 allgemeine Datenregister und 128 Gleitkomma-Datenregister für den IA-64-Prozessor, wobei jedoch nur der `REGISTER_IA64_R0`-Wert und der `REGISTER_IA64_F0`-Wert bereitgestellt werden. Die anderen Werte können wie folgt bestimmt werden:  
  
- Fügen Sie `REGISTER_IA64_R0` die Registernummer für die Werte `REGISTER_IA64_R1` bis `REGISTER_IA64_R127` hinzu, was dem Datenregister 1 bis 127 für den IA-64-Prozessor entspricht.  
  
- Fügen Sie `REGISTER_IA64_F0` die Registernummer für die Werte `REGISTER_IA64_F1` bis `REGISTER_IA64_F127` hinzu, was dem FP-Datenregister 1 bis 127 für den IA-64-Prozessor entspricht.  
  
 Wenn Sie zum Bespiel das Datenregister 83 für den IA-64-Prozessor festlegen müssen, verwenden Sie `REGISTER_IA64_R0` + 83.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
