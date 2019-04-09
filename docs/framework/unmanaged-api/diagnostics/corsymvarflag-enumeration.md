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
ms.openlocfilehash: 0c797378f5e13f39c1c786237a3a7b9cf577fccc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198854"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="81c05-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="81c05-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="81c05-103">Gibt an, ob eine Variable vom Compiler generierter ist.</span><span class="sxs-lookup"><span data-stu-id="81c05-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81c05-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="81c05-105">Member</span><span class="sxs-lookup"><span data-stu-id="81c05-105">Members</span></span>  
  
|<span data-ttu-id="81c05-106">Member</span><span class="sxs-lookup"><span data-stu-id="81c05-106">Member</span></span>|<span data-ttu-id="81c05-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c05-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="81c05-108">Gibt an, dass die angegebene Variable Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="81c05-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81c05-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81c05-109">Requirements</span></span>  
 <span data-ttu-id="81c05-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="81c05-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c05-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81c05-111">See also</span></span>

- [<span data-ttu-id="81c05-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="81c05-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
