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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914640"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="eeaf9-102">SYMLINEDELTA-Struktur</span><span class="sxs-lookup"><span data-stu-id="eeaf9-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="eeaf9-103">Enthält Informationen, die an den Symbol-Handler zu Methoden, die Bearbeitungsvorgängen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="eeaf9-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeaf9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeaf9-104">Syntax</span></span>  
  
```  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="eeaf9-105">Member</span><span class="sxs-lookup"><span data-stu-id="eeaf9-105">Members</span></span>  
  
|<span data-ttu-id="eeaf9-106">Member</span><span class="sxs-lookup"><span data-stu-id="eeaf9-106">Member</span></span>|<span data-ttu-id="eeaf9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eeaf9-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="eeaf9-108">Die Methode die Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="eeaf9-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="eeaf9-109">Die Anzahl der Zeilen, die die Methode verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="eeaf9-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eeaf9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eeaf9-110">Requirements</span></span>  
 <span data-ttu-id="eeaf9-111">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="eeaf9-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeaf9-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeaf9-112">See also</span></span>

- [<span data-ttu-id="eeaf9-113">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="eeaf9-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
