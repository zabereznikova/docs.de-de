---
title: ISymUnmanagedWriter3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: 006045ce101884119f676e4f6324815eb21a10a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614655"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="97476-102">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97476-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="97476-103">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="97476-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="97476-104">Diese Schnittstelle erweitert die [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="97476-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97476-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="97476-105">Methods</span></span>  
  
|<span data-ttu-id="97476-106">Methode</span><span class="sxs-lookup"><span data-stu-id="97476-106">Method</span></span>|<span data-ttu-id="97476-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="97476-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97476-108">Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="97476-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="97476-109">Führt einen Commit für die bisher geschriebenen Änderungen in den Stream aus.</span><span class="sxs-lookup"><span data-stu-id="97476-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="97476-110">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="97476-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="97476-111">Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.</span><span class="sxs-lookup"><span data-stu-id="97476-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97476-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97476-112">Requirements</span></span>  
 <span data-ttu-id="97476-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="97476-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97476-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97476-114">See also</span></span>

- [<span data-ttu-id="97476-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="97476-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="97476-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97476-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="97476-117">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97476-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
