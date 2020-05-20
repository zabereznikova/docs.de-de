---
title: CorSymVarFlag-Enumeration
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: d41e048b67d4bc7159f6dd5266457651f1658290
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420590"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="0795a-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0795a-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="0795a-103">Gibt an, ob eine Variable vom Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0795a-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0795a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0795a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0795a-105">Member</span><span class="sxs-lookup"><span data-stu-id="0795a-105">Members</span></span>  
  
|<span data-ttu-id="0795a-106">Member</span><span class="sxs-lookup"><span data-stu-id="0795a-106">Member</span></span>|<span data-ttu-id="0795a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0795a-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="0795a-108">Gibt an, dass die angegebene Variable vom Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0795a-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0795a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0795a-109">Requirements</span></span>  
 <span data-ttu-id="0795a-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0795a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0795a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0795a-111">See also</span></span>

- [<span data-ttu-id="0795a-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0795a-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
