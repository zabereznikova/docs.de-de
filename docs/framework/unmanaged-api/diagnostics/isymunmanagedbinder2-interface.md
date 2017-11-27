---
title: ISymUnmanagedBinder2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c276f0abedf4ccab92770af649a8dd0afb6d39d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="79803-102">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79803-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="79803-103">Stellt einen Symbolbinder für nicht verwalteten Code dar und erweitert die [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="79803-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79803-104">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="79803-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="79803-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="79803-105">Methods</span></span>  
  
|<span data-ttu-id="79803-106">Methode</span><span class="sxs-lookup"><span data-stu-id="79803-106">Method</span></span>|<span data-ttu-id="79803-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79803-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="79803-108">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="79803-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="79803-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Schnittstelle, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="79803-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="79803-110">Bietet eine ausführliche Suche als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="79803-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79803-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="79803-111">Requirements</span></span>  
 <span data-ttu-id="79803-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="79803-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79803-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79803-113">See Also</span></span>  
 [<span data-ttu-id="79803-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="79803-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="79803-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79803-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="79803-116">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79803-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
