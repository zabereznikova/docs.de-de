---
title: CorSymAddrKind-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymAddrKind
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymAddrKind
helpviewer_keywords: CorSymAddrKind enumeration [.NET Framework debugging]
ms.assetid: 3ef841c2-cade-42ee-ba34-2ef91d6d0879
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56bb55d9c9f85ae8f8112f16dcf552295699826d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="c4a6d-102">CorSymAddrKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c4a6d-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="c4a6d-103">Gibt den Typ der Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4a6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4a6d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c4a6d-105">Member</span><span class="sxs-lookup"><span data-stu-id="c4a6d-105">Members</span></span>  
  
|<span data-ttu-id="c4a6d-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4a6d-106">Member</span></span>|<span data-ttu-id="c4a6d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4a6d-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="c4a6d-108">Gibt einen Microsoft intermediate Language (MSIL) lokale Variablen oder Parameter Index an.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="c4a6d-109">Gibt eine relative virtuelle Adresse in einem Modul an.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="c4a6d-110">Gibt einen CPU-Register an.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="c4a6d-111">Gibt an, dass die erste Adresse eines Registers und die zweite Adresse ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="c4a6d-112">Gibt einen Offset von einer Basisadresse an.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="c4a6d-113">Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist und die zweite Adresse der hohe Bereich.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="c4a6d-114">Gibt an, dass die erste Adresse der niedrigen Teil eines Registers ist, das zweite der hohe Bereich ist und das dritte ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="c4a6d-115">Gibt an, dass die erste Adresse eines Registers, das zweite ein Offset ist, und der dritte der hohe Bereich des Registers ist.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="c4a6d-116">Gibt an, dass die erste Adresse der Anfang eines Felds ist und die zweite Adresse die Feldlänge ist.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="c4a6d-117">Gibt an, dass die erste Adresse der Abschnitt ist und die zweite Adresse ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="c4a6d-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4a6d-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-118">Requirements</span></span>  
 <span data-ttu-id="c4a6d-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c4a6d-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a6d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4a6d-120">See Also</span></span>  
 [<span data-ttu-id="c4a6d-121">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c4a6d-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
