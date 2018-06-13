---
title: ISymUnmanagedBinder-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7bbdc4b1f15c8dbb154ed7b967bb21c61d11782a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425551"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="01da5-102">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01da5-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="01da5-103">Stellt einen Symbolbinder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="01da5-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="01da5-104">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="01da5-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01da5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="01da5-105">Methods</span></span>  
  
|<span data-ttu-id="01da5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="01da5-106">Method</span></span>|<span data-ttu-id="01da5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01da5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01da5-108">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="01da5-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="01da5-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="01da5-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="01da5-110">GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="01da5-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="01da5-111">Gibt bei Angabe einer Metadatenschnittstelle und einen Stream, der den Symbolspeicher enthält, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="01da5-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01da5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01da5-112">Requirements</span></span>  
 <span data-ttu-id="01da5-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="01da5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01da5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01da5-114">See Also</span></span>  
 [<span data-ttu-id="01da5-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="01da5-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="01da5-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01da5-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="01da5-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01da5-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
