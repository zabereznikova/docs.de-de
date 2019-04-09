---
title: SYMLINEDELTA-Struktur
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fabc8f77b12865d0d971b5934d7de27b52f3e813
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159483"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="0d473-102">SYMLINEDELTA-Struktur</span><span class="sxs-lookup"><span data-stu-id="0d473-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="0d473-103">Enthält Informationen, die an den Symbol-Handler zu Methoden, die Bearbeitungsvorgängen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="0d473-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d473-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d473-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="0d473-105">Member</span><span class="sxs-lookup"><span data-stu-id="0d473-105">Members</span></span>  
  
|<span data-ttu-id="0d473-106">Member</span><span class="sxs-lookup"><span data-stu-id="0d473-106">Member</span></span>|<span data-ttu-id="0d473-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d473-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="0d473-108">Die Methode die Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="0d473-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="0d473-109">Die Anzahl der Zeilen, die die Methode verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="0d473-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d473-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d473-110">Requirements</span></span>  
 <span data-ttu-id="0d473-111">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="0d473-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d473-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d473-112">See also</span></span>

- [<span data-ttu-id="0d473-113">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="0d473-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
