---
title: ISymUnmanagedBinder-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5061ce28c4a09f445267c99420bf1942d99076bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="942f3-102">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="942f3-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="942f3-103">Stellt einen Symbolbinder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="942f3-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="942f3-104">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="942f3-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="942f3-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="942f3-105">Methods</span></span>  
  
|<span data-ttu-id="942f3-106">Methode</span><span class="sxs-lookup"><span data-stu-id="942f3-106">Method</span></span>|<span data-ttu-id="942f3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="942f3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="942f3-108">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="942f3-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="942f3-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Struktur, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="942f3-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="942f3-110">GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="942f3-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="942f3-111">Gibt bei Angabe einer Metadatenschnittstelle und einen Stream, der den Symbolspeicher enthält, den richtigen <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`>-Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="942f3-111">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="942f3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="942f3-112">Requirements</span></span>  
 <span data-ttu-id="942f3-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="942f3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942f3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="942f3-114">See Also</span></span>  
 [<span data-ttu-id="942f3-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="942f3-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="942f3-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="942f3-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="942f3-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="942f3-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
