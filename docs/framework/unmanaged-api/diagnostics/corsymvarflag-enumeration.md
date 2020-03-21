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
ms.openlocfilehash: 21e92d8f2fb80c4c41d516ef281bf4fc8a75f4e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176642"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="5ebd0-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5ebd0-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="5ebd0-103">Gibt an, ob eine Variable vom Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5ebd0-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebd0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ebd0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="5ebd0-105">Members</span><span class="sxs-lookup"><span data-stu-id="5ebd0-105">Members</span></span>  
  
|<span data-ttu-id="5ebd0-106">Member</span><span class="sxs-lookup"><span data-stu-id="5ebd0-106">Member</span></span>|<span data-ttu-id="5ebd0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ebd0-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="5ebd0-108">Gibt an, dass die angegebene Variable vom Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="5ebd0-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ebd0-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ebd0-109">Requirements</span></span>  
 <span data-ttu-id="5ebd0-110">**Kopfzeile:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5ebd0-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebd0-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ebd0-111">See also</span></span>

- [<span data-ttu-id="5ebd0-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5ebd0-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
