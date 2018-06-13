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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6a9c5ff91989fc1ad7da4e23df0e80d9d74ec7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424975"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="0259e-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0259e-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="0259e-103">Gibt an, ob eine Variable vom Compiler generierte ist.</span><span class="sxs-lookup"><span data-stu-id="0259e-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0259e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0259e-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0259e-105">Member</span><span class="sxs-lookup"><span data-stu-id="0259e-105">Members</span></span>  
  
|<span data-ttu-id="0259e-106">Member</span><span class="sxs-lookup"><span data-stu-id="0259e-106">Member</span></span>|<span data-ttu-id="0259e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0259e-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="0259e-108">Gibt an, dass die angegebene Variable Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0259e-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0259e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0259e-109">Requirements</span></span>  
 <span data-ttu-id="0259e-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0259e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0259e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0259e-111">See Also</span></span>  
 [<span data-ttu-id="0259e-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0259e-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
