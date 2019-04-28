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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763649"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="27941-102">CorSymVarFlag-Enumeration</span><span class="sxs-lookup"><span data-stu-id="27941-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="27941-103">Gibt an, ob eine Variable vom Compiler generierter ist.</span><span class="sxs-lookup"><span data-stu-id="27941-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27941-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27941-104">Syntax</span></span>  
  
```  
typedef enum CorSymVarFlag   
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="27941-105">Member</span><span class="sxs-lookup"><span data-stu-id="27941-105">Members</span></span>  
  
|<span data-ttu-id="27941-106">Member</span><span class="sxs-lookup"><span data-stu-id="27941-106">Member</span></span>|<span data-ttu-id="27941-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27941-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="27941-108">Gibt an, dass die angegebene Variable Compiler generiert wird.</span><span class="sxs-lookup"><span data-stu-id="27941-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27941-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27941-109">Requirements</span></span>  
 <span data-ttu-id="27941-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="27941-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27941-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27941-111">See also</span></span>

- [<span data-ttu-id="27941-112">Diagnosesymbolspeicher-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="27941-112">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
