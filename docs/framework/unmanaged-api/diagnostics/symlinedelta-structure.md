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
ms.openlocfilehash: dd45703540f8dc41b746ca03b4f09d74186aa9aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690940"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="2985a-102">SYMLINEDELTA-Struktur</span><span class="sxs-lookup"><span data-stu-id="2985a-102">SYMLINEDELTA Structure</span></span>

<span data-ttu-id="2985a-103">Stellt Informationen für den Symbol Handler über Methoden bereit, die aufgrund von Änderungen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="2985a-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2985a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2985a-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="2985a-105">Member</span><span class="sxs-lookup"><span data-stu-id="2985a-105">Members</span></span>  
  
|<span data-ttu-id="2985a-106">Member</span><span class="sxs-lookup"><span data-stu-id="2985a-106">Member</span></span>|<span data-ttu-id="2985a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2985a-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="2985a-108">Das Metadatentoken der Methode.</span><span class="sxs-lookup"><span data-stu-id="2985a-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="2985a-109">Die Anzahl der Zeilen, die die Methode verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="2985a-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2985a-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2985a-110">Requirements</span></span>  

 <span data-ttu-id="2985a-111">**Header:** Corsym. idl</span><span class="sxs-lookup"><span data-stu-id="2985a-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2985a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2985a-112">See also</span></span>

- [<span data-ttu-id="2985a-113">Diagnosesymbolspeicher-Strukturen</span><span class="sxs-lookup"><span data-stu-id="2985a-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
