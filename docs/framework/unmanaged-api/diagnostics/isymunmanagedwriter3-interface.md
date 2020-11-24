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
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683289"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="337fe-102">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="337fe-102">ISymUnmanagedWriter3 Interface</span></span>

<span data-ttu-id="337fe-103">Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit.</span><span class="sxs-lookup"><span data-stu-id="337fe-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="337fe-104">Diese Schnittstelle erweitert die [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="337fe-104">This interface extends the [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="337fe-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="337fe-105">Methods</span></span>  
  
|<span data-ttu-id="337fe-106">Methode</span><span class="sxs-lookup"><span data-stu-id="337fe-106">Method</span></span>|<span data-ttu-id="337fe-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="337fe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="337fe-108">Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="337fe-108">Commit Method</span></span>](isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="337fe-109">Führt einen Commit für die bisher geschriebenen Änderungen in den Stream aus.</span><span class="sxs-lookup"><span data-stu-id="337fe-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="337fe-110">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="337fe-110">OpenMethod2 Method</span></span>](isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="337fe-111">Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.</span><span class="sxs-lookup"><span data-stu-id="337fe-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="337fe-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="337fe-112">Requirements</span></span>  

 <span data-ttu-id="337fe-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="337fe-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337fe-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="337fe-114">See also</span></span>

- [<span data-ttu-id="337fe-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="337fe-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="337fe-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="337fe-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="337fe-117">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="337fe-117">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
