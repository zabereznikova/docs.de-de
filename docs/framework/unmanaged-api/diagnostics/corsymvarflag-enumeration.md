---
title: CorSymVarFlag-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSymVarFlag
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSymVarFlag
helpviewer_keywords: CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: edbbc8109eb44494c7f4fac0ed8756e23bdc955b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="4c04b-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4c04b-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="4c04b-103">Gibt an, ob eine Variable vom Compiler generierte ist.</span><span class="sxs-lookup"><span data-stu-id="4c04b-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c04b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c04b-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="4c04b-105">Member</span><span class="sxs-lookup"><span data-stu-id="4c04b-105">Members</span></span>  
  
|<span data-ttu-id="4c04b-106">Member</span><span class="sxs-lookup"><span data-stu-id="4c04b-106">Member</span></span>|<span data-ttu-id="4c04b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c04b-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="4c04b-108">Gibt an, dass die angegebene Variable Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c04b-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c04b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c04b-109">Requirements</span></span>  
 <span data-ttu-id="4c04b-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4c04b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c04b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c04b-111">See Also</span></span>  
 [<span data-ttu-id="4c04b-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4c04b-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
