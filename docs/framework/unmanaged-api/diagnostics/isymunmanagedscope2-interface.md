---
title: ISymUnmanagedScope2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 886ba693183a6b99eb03635e95a9661d105de40e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610859"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="9d715-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d715-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="9d715-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="9d715-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="9d715-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](isymunmanagedscope-interface.md) -Schnittstelle um Methoden, die Informationen zu konstanten erhalten, die innerhalb des Bereichs definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9d715-104">This interface extends the [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d715-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9d715-105">Methods</span></span>  
  
|<span data-ttu-id="9d715-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9d715-106">Method</span></span>|<span data-ttu-id="9d715-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9d715-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d715-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="9d715-108">GetConstantCount Method</span></span>](isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="9d715-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="9d715-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="9d715-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="9d715-110">GetConstants Method</span></span>](isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="9d715-111">Ruft die in diesem Bereich definierten lokalen Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="9d715-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d715-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d715-112">Requirements</span></span>  
 <span data-ttu-id="9d715-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="9d715-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d715-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d715-114">See also</span></span>

- [<span data-ttu-id="9d715-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9d715-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="9d715-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d715-116">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
