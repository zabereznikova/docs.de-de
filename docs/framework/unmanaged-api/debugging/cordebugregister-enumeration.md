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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bed3c461935c5a2bc912ed9ed16d147fddaf8a1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739653"
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="9d6dd-102">CorDebugRegister-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9d6dd-102">CorDebugRegister Enumeration</span></span>
<span data-ttu-id="9d6dd-103">Gibt die einer bestimmten Prozessorarchitektur zugeordneten Register an.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-103">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d6dd-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9d6dd-105">Member</span><span class="sxs-lookup"><span data-stu-id="9d6dd-105">Members</span></span>  
  
|<span data-ttu-id="9d6dd-106">Member</span><span class="sxs-lookup"><span data-stu-id="9d6dd-106">Member</span></span>|<span data-ttu-id="9d6dd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d6dd-107">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="9d6dd-108">Ein Anweisungszeigerregister für einen beliebigen Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-108">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="9d6dd-109">Ein Stapelzeigerregister für einen beliebigen Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-109">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="9d6dd-110">Ein Framezeigerregister für einen beliebigen Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-110">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="9d6dd-111">Das Anweisungszeigerregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-111">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="9d6dd-112">Das Stapelzeigerregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-112">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="9d6dd-113">Das Basiszeigerregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-113">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="9d6dd-114">Das A-Datenregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-114">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="9d6dd-115">Das C-Datenregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-115">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="9d6dd-116">Das D-Datenregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-116">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="9d6dd-117">Das B-Datenregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-117">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="9d6dd-118">Das Quellindexregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-118">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="9d6dd-119">Das Zielindexregister für den x86-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-119">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="9d6dd-120">Das Stapelregister 0 im x86-Gleitkommaprozessor (FP).</span><span class="sxs-lookup"><span data-stu-id="9d6dd-120">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="9d6dd-121">Das Stapelregister 1 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-121">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="9d6dd-122">Das Stapelregister 2 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-122">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="9d6dd-123">Das Stapelregister 3 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-123">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="9d6dd-124">Das Stapelregister 4 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-124">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="9d6dd-125">Das Stapelregister 5 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-125">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="9d6dd-126">Das Stapelregister 6 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-126">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="9d6dd-127">Das Stapelregister 7 für den x86-FP-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-127">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="9d6dd-128">Das Anweisungszeigerregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-128">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="9d6dd-129">Das Stapelzeigerregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-129">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="9d6dd-130">Das Basiszeigerregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-130">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="9d6dd-131">Das A-Datenregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-131">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="9d6dd-132">Das C-Datenregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-132">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="9d6dd-133">Das D-Datenregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-133">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="9d6dd-134">Das B-Datenregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-134">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="9d6dd-135">Das Quellindexregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-135">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="9d6dd-136">Das Zielindexregister für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-136">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="9d6dd-137">Das Datenregister 8 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-137">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="9d6dd-138">Das Datenregister 9 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-138">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="9d6dd-139">Das Datenregister 10 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-139">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="9d6dd-140">Das Datenregister 11 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-140">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="9d6dd-141">Das Datenregister 12 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-141">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="9d6dd-142">Das Datenregister 13 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-142">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="9d6dd-143">Das Datenregister 14 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-143">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="9d6dd-144">Das Datenregister 15 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-144">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="9d6dd-145">Das Multimediaregister 0 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-145">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="9d6dd-146">Das Multimediaregister 1 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-146">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="9d6dd-147">Das Multimediaregister 2 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-147">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="9d6dd-148">Das Multimediaregister 3 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-148">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="9d6dd-149">Das Multimediaregister 4 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-149">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="9d6dd-150">Das Multimediaregister 5 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-150">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="9d6dd-151">Das Multimediaregister 6 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-151">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="9d6dd-152">Das Multimediaregister 7 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-152">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="9d6dd-153">Das Multimediaregister 8 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-153">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="9d6dd-154">Das Multimediaregister 9 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-154">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="9d6dd-155">Das Multimediaregister 10 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-155">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="9d6dd-156">Das Multimediaregister 11 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-156">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="9d6dd-157">Das Multimediaregister 12 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-157">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="9d6dd-158">Das Multimediaregister 13 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-158">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="9d6dd-159">Das Multimediaregister 14 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-159">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="9d6dd-160">Das Multimediaregister 15 für den AMD64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-160">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="9d6dd-161">Das Stapelzeigerregister für den IA-64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-161">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="9d6dd-162">Das Datenregister 0 für den IA-64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-162">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="9d6dd-163">Das FP-Datenregister 0 für den IA-64-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-163">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="9d6dd-164">Das Programmzählerregister (R15) für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-164">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="9d6dd-165">Das Stapelzeigerregister (R13) für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-165">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="9d6dd-166">Das Datenregister R0 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-166">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="9d6dd-167">Das Datenregister R1 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-167">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="9d6dd-168">Das Datenregister R2 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-168">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="9d6dd-169">Das Datenregister R3 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-169">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="9d6dd-170">Register R4 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-170">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="9d6dd-171">Register R5 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-171">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="9d6dd-172">Register R6 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-172">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="9d6dd-173">Register R7 (der THUMB-Framezeiger) für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-173">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="9d6dd-174">Register R8 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-174">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="9d6dd-175">Register R9 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-175">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="9d6dd-176">Register R10 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-176">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="9d6dd-177">Der Framezeiger für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-177">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="9d6dd-178">Register R12 für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-178">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="9d6dd-179">Das Link-Register (R14) für den ARM-Prozessor.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-179">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d6dd-180">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d6dd-180">Remarks</span></span>  
 <span data-ttu-id="9d6dd-181">Es gibt 128 allgemeine Datenregister und 128 Gleitkomma-Datenregister für den IA-64-Prozessor, wobei jedoch nur der `REGISTER_IA64_R0`-Wert und der `REGISTER_IA64_F0`-Wert bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-181">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="9d6dd-182">Die anderen Werte können wie folgt bestimmt werden:</span><span class="sxs-lookup"><span data-stu-id="9d6dd-182">The other values can be determined as follows:</span></span>  
  
- <span data-ttu-id="9d6dd-183">Fügen Sie `REGISTER_IA64_R0` die Registernummer für die Werte `REGISTER_IA64_R1` bis `REGISTER_IA64_R127` hinzu, was dem Datenregister 1 bis 127 für den IA-64-Prozessor entspricht.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-183">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
- <span data-ttu-id="9d6dd-184">Fügen Sie `REGISTER_IA64_F0` die Registernummer für die Werte `REGISTER_IA64_F1` bis `REGISTER_IA64_F127` hinzu, was dem FP-Datenregister 1 bis 127 für den IA-64-Prozessor entspricht.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-184">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="9d6dd-185">Wenn Sie zum Bespiel das Datenregister 83 für den IA-64-Prozessor festlegen müssen, verwenden Sie `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="9d6dd-185">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d6dd-186">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d6dd-186">Requirements</span></span>  
 <span data-ttu-id="9d6dd-187">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d6dd-187">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d6dd-188">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d6dd-188">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d6dd-189">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d6dd-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d6dd-190">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d6dd-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6dd-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d6dd-191">See also</span></span>

- [<span data-ttu-id="9d6dd-192">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9d6dd-192">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
