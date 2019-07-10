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
ms.openlocfilehash: d98ebed2eb853d5dc8177b0b044bf654c3978494
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744351"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="cec7f-102">SYMLINEDELTA-Struktur</span><span class="sxs-lookup"><span data-stu-id="cec7f-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="cec7f-103">Enthält Informationen, die an den Symbol-Handler zu Methoden, die Bearbeitungsvorgängen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="cec7f-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cec7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cec7f-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="cec7f-105">Member</span><span class="sxs-lookup"><span data-stu-id="cec7f-105">Members</span></span>  
  
|<span data-ttu-id="cec7f-106">Member</span><span class="sxs-lookup"><span data-stu-id="cec7f-106">Member</span></span>|<span data-ttu-id="cec7f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cec7f-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="cec7f-108">Die Methode die Metadaten-Token.</span><span class="sxs-lookup"><span data-stu-id="cec7f-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="cec7f-109">Die Anzahl der Zeilen, die die Methode verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="cec7f-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cec7f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cec7f-110">Requirements</span></span>  
 <span data-ttu-id="cec7f-111">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="cec7f-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec7f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cec7f-112">See also</span></span>

- [<span data-ttu-id="cec7f-113">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="cec7f-113">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
