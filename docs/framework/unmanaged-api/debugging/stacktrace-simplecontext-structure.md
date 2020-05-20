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
ms.openlocfilehash: 45ae947cda5b4ddadfb10f5b2bdc78a95f031703
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420686"
---
# <a name="stacktrace_simplecontext-structure"></a><span data-ttu-id="ec92c-102">StackTrace_SimpleContext-Struktur</span><span class="sxs-lookup"><span data-stu-id="ec92c-102">StackTrace_SimpleContext Structure</span></span>
<span data-ttu-id="ec92c-103">Stellt einen einfachen Kontext bereit, der statt einer vollständigen `CONTEXT`-Struktur verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec92c-103">Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec92c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec92c-104">Syntax</span></span>  
  
```cpp  
struct StackTrace_SimpleContext  
{  
    ULONG64 StackOffset;       // ESP on x86  
    ULONG64 FrameOffset;       // EBP on x86  
    ULONG64 InstructionOffset; // EIP on x86  
};  
```  
  
## <a name="members"></a><span data-ttu-id="ec92c-105">Member</span><span class="sxs-lookup"><span data-stu-id="ec92c-105">Members</span></span>  
  
|<span data-ttu-id="ec92c-106">Member</span><span class="sxs-lookup"><span data-stu-id="ec92c-106">Member</span></span>|<span data-ttu-id="ec92c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec92c-107">Description</span></span>|  
|------------|-----------------|  
|`StackOffset`|<span data-ttu-id="ec92c-108">Der Stapelzeiger oder der Eingabe Stapelzeiger (ESP) auf x86-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="ec92c-108">The stack pointer, or the enter stack pointer (ESP) on x86 platforms.</span></span>|  
|`FrameOffset`|<span data-ttu-id="ec92c-109">Der Frame Offset oder das EBP-Register auf x86-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="ec92c-109">The frame offset, or the EBP register on x86 platforms.</span></span>|  
|`InstructionOffset`|<span data-ttu-id="ec92c-110">Der Anweisungs Zeiger oder der Eingabe Anweisungs Zeiger (EIP) auf x86-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="ec92c-110">The instruction pointer, or the enter instruction pointer (EIP) on x86 platforms.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec92c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec92c-111">Remarks</span></span>  
 <span data-ttu-id="ec92c-112">Da Stapel Überwachungsfunktionen in der Regel nur die Adresse, den Frame Offset und die Stapel Adresse zurückgeben müssen, können Sie optional die `SimpleContext` Struktur anstelle einer großen `CONTEXT` Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec92c-112">Because stack trace functions typically need to return only the address, frame offset, and stack address, you can optionally use the `SimpleContext` structure instead of a large `CONTEXT` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec92c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec92c-113">Requirements</span></span>  
 <span data-ttu-id="ec92c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec92c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec92c-115">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="ec92c-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="ec92c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec92c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec92c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec92c-117">See also</span></span>

- [<span data-ttu-id="ec92c-118">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ec92c-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ec92c-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ec92c-119">Debugging</span></span>](index.md)
