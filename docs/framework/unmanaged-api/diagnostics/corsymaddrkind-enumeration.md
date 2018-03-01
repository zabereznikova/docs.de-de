---
title: CorSymAddrKind-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorSymAddrKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymAddrKind
helpviewer_keywords:
- CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 300913f9ea89044e425f9f05856d13fa15cdc015
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="33498-102">CorSymAddrKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="33498-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="33498-103">Gibt den Typ der Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="33498-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33498-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33498-104">Syntax</span></span>  
  
```  
typedef enum CorSymAddrKind  
{  
    ADDR_IL_OFFSET          = 1,  
    ADDR_NATIVE_RVA         = 2,  
    ADDR_NATIVE_REGISTER    = 3,  
    ADDR_NATIVE_REGREL      = 4,  
    ADDR_NATIVE_OFFSET      = 5,  
    ADDR_NATIVE_REGREG      = 6,  
    ADDR_NATIVE_REGSTK      = 7,  
    ADDR_NATIVE_STKREG      = 8,  
    ADDR_BITFIELD           = 9,  
    ADDR_NATIVE_ISECTOFFSET = 10  
} CorSymAddrKind;  
```  
  
## <a name="members"></a><span data-ttu-id="33498-105">Member</span><span class="sxs-lookup"><span data-stu-id="33498-105">Members</span></span>  
  
|<span data-ttu-id="33498-106">Member</span><span class="sxs-lookup"><span data-stu-id="33498-106">Member</span></span>|<span data-ttu-id="33498-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33498-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="33498-108">Gibt einen Microsoft intermediate Language (MSIL) lokale Variablen oder Parameter Index an.</span><span class="sxs-lookup"><span data-stu-id="33498-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="33498-109">Gibt eine relative virtuelle Adresse in einem Modul an.</span><span class="sxs-lookup"><span data-stu-id="33498-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="33498-110">Gibt einen CPU-Register an.</span><span class="sxs-lookup"><span data-stu-id="33498-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="33498-111">Gibt an, dass die erste Adresse eines Registers und die zweite Adresse ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="33498-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="33498-112">Gibt einen Offset von einer Basisadresse an.</span><span class="sxs-lookup"><span data-stu-id="33498-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="33498-113">Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist und die zweite Adresse der hohe Bereich.</span><span class="sxs-lookup"><span data-stu-id="33498-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="33498-114">Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist, das zweite der hohe Bereich ist und das dritte ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="33498-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="33498-115">Gibt an, dass die erste Adresse eines Registers, das zweite ein Offset ist, und der dritte der hohe Bereich des Registers ist.</span><span class="sxs-lookup"><span data-stu-id="33498-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="33498-116">Gibt an, dass die erste Adresse der Anfang eines Felds ist und die zweite Adresse die Feldlänge ist.</span><span class="sxs-lookup"><span data-stu-id="33498-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="33498-117">Gibt an, dass die erste Adresse der Abschnitt ist und die zweite Adresse ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="33498-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33498-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33498-118">Requirements</span></span>  
 <span data-ttu-id="33498-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33498-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33498-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33498-120">See Also</span></span>  
 [<span data-ttu-id="33498-121">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="33498-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
