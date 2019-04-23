---
title: CorSymAddrKind-Enumeration
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adef1010d08561c0a0fe38480fe0d2f519a80b49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133522"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="13822-102">CorSymAddrKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="13822-102">CorSymAddrKind Enumeration</span></span>
<span data-ttu-id="13822-103">Gibt den Typ der Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="13822-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13822-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13822-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="13822-105">Member</span><span class="sxs-lookup"><span data-stu-id="13822-105">Members</span></span>  
  
|<span data-ttu-id="13822-106">Member</span><span class="sxs-lookup"><span data-stu-id="13822-106">Member</span></span>|<span data-ttu-id="13822-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13822-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="13822-108">Gibt einen Microsoft intermediate Language (MSIL) lokale Variable oder Parameter Index an.</span><span class="sxs-lookup"><span data-stu-id="13822-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="13822-109">Gibt eine relative virtuelle Adresse in einem Modul an.</span><span class="sxs-lookup"><span data-stu-id="13822-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="13822-110">Gibt ein CPU-Register an.</span><span class="sxs-lookup"><span data-stu-id="13822-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="13822-111">Gibt an, dass die erste Adresse ein Register ist und die zweite Adresse eine Abweichung ist.</span><span class="sxs-lookup"><span data-stu-id="13822-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="13822-112">Gibt an, ein Offset von einer Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="13822-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="13822-113">Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, und die zweite Adresse der hohe Teil ist.</span><span class="sxs-lookup"><span data-stu-id="13822-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="13822-114">Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, das zweite der hohe Teil ist, und die dritte ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="13822-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="13822-115">Gibt an, dass die erste Adresse ein Register ist, die zweite ein Offset ist und der dritte der hohe Teil der Registrierung ist.</span><span class="sxs-lookup"><span data-stu-id="13822-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="13822-116">Gibt an, dass die erste Adresse der Anfang eines Felds ist, und die zweite Adresse die Feldlänge stellt.</span><span class="sxs-lookup"><span data-stu-id="13822-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="13822-117">Gibt an, dass die erste Adresse der Abschnitt ist, und die zweite Adresse eine Abweichung ist.</span><span class="sxs-lookup"><span data-stu-id="13822-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13822-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13822-118">Requirements</span></span>  
 <span data-ttu-id="13822-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13822-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13822-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13822-120">See also</span></span>

- [<span data-ttu-id="13822-121">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="13822-121">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
