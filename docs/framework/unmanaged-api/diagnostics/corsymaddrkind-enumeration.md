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
ms.openlocfilehash: f71d8956e8706cdc71b94b6e6e2e8210e5b9161e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725234"
---
# <a name="corsymaddrkind-enumeration"></a><span data-ttu-id="c4c0e-102">CorSymAddrKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c4c0e-102">CorSymAddrKind Enumeration</span></span>

<span data-ttu-id="c4c0e-103">Gibt den Typ der Speicheradresse an.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-103">Indicates the type of memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4c0e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c4c0e-105">Member</span><span class="sxs-lookup"><span data-stu-id="c4c0e-105">Members</span></span>  
  
|<span data-ttu-id="c4c0e-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4c0e-106">Member</span></span>|<span data-ttu-id="c4c0e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4c0e-107">Description</span></span>|  
|------------|-----------------|  
|`ADDR_IL_OFFSET`|<span data-ttu-id="c4c0e-108">Gibt eine lokale MSIL-Variable (Microsoft Intermediate Language) oder einen Parameter Index an.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-108">Indicates a Microsoft intermediate language (MSIL) local variable or parameter index.</span></span>|  
|`ADDR_NATIVE_RVA`|<span data-ttu-id="c4c0e-109">Gibt eine relative virtuelle Adresse in einem Modul an.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-109">Indicates a relative virtual address into a module.</span></span>|  
|`ADDR_NATIVE_REGISTER`|<span data-ttu-id="c4c0e-110">Gibt ein CPU-Register an.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-110">Indicates a CPU register.</span></span>|  
|`ADDR_NATIVE_REGREL`|<span data-ttu-id="c4c0e-111">Gibt an, dass die erste Adresse ein Register ist, und die zweite Adresse ist ein Offset.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-111">Indicates that the first address is a register and the second address is an offset.</span></span>|  
|`ADDR_NATIVE_OFFSET`|<span data-ttu-id="c4c0e-112">Gibt einen Offset von einer Basisadresse an.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-112">Indicates an offset from a base address.</span></span>|  
|`ADDR_NATIVE_REGREG`|<span data-ttu-id="c4c0e-113">Gibt an, dass die erste Adresse der niedrige Anteil eines Register ist, und die zweite Adresse ist der hohe Anteil.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-113">Indicates that the first address is the low portion of a register, and the second address is the high portion.</span></span>|  
|`ADDR_NATIVE_REGSTK`|<span data-ttu-id="c4c0e-114">Gibt an, dass die erste Adresse der niedrige Teil eines Registers ist, der zweite der hohe Anteil und der dritte ein Offset.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-114">Indicates that the first address is the low portion of a register, the second is the high portion, and the third is an offset.</span></span>|  
|`ADDR_NATIVE_STKREG`|<span data-ttu-id="c4c0e-115">Gibt an, dass die erste Adresse ein Register ist, der zweite ein Offset und der dritte der große Teil des Registers.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-115">Indicates that the first address is a register, the second is an offset, and the third is the high portion of the register.</span></span>|  
|`ADDR_BITFIELD`|<span data-ttu-id="c4c0e-116">Gibt an, dass die erste Adresse der Anfang eines Felds und die zweite Adresse die Feldlänge ist.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-116">Indicates that the first address is the start of a field and the second address is the field length.</span></span>|  
|`ADDR_NATIVE_ISECTOFFSET`|<span data-ttu-id="c4c0e-117">Gibt an, dass die erste Adresse der Abschnitt und die zweite Adresse ein Offset ist.</span><span class="sxs-lookup"><span data-stu-id="c4c0e-117">Indicates that the first address is the section and the second address is an offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4c0e-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4c0e-118">Requirements</span></span>  

 <span data-ttu-id="c4c0e-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c4c0e-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c0e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4c0e-120">See also</span></span>

- [<span data-ttu-id="c4c0e-121">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c4c0e-121">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
