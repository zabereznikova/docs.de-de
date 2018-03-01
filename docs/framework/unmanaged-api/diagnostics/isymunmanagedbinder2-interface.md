---
title: ISymUnmanagedBinder2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0fff140f6848b91e811ef4546a3e8fd50eb61e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="d2e55-102">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2e55-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="d2e55-103">Stellt einen Symbolbinder für nicht verwalteten Code dar und erweitert die [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d2e55-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e55-104">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2e55-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2e55-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d2e55-105">Methods</span></span>  
  
|<span data-ttu-id="d2e55-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d2e55-106">Method</span></span>|<span data-ttu-id="d2e55-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2e55-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2e55-108">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="d2e55-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="d2e55-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> Schnittstelle, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="d2e55-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="d2e55-110">Bietet eine ausführliche Suche als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d2e55-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d2e55-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2e55-111">Requirements</span></span>  
 <span data-ttu-id="d2e55-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d2e55-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e55-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2e55-113">See Also</span></span>  
 [<span data-ttu-id="d2e55-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2e55-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="d2e55-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2e55-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="d2e55-116">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2e55-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
