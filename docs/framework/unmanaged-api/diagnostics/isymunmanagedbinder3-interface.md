---
title: ISymUnmanagedBinder3-Schnittstelle
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
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c93275fc32e68f49618d93bdd0b54f1970121ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="82705-102">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82705-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="82705-103">Erweitert die Symbol-Binder-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82705-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="82705-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82705-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82705-105">Es ist ein Sicherheitsrisiko zu eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle öffnen.</span><span class="sxs-lookup"><span data-stu-id="82705-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="82705-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="82705-106">Methods</span></span>  
  
|<span data-ttu-id="82705-107">Methode</span><span class="sxs-lookup"><span data-stu-id="82705-107">Method</span></span>|<span data-ttu-id="82705-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82705-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="82705-109">GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="82705-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="82705-110">Ermöglicht es dem Benutzer zu implementieren, oder geben Sie entweder über Rückruf eine `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen</span><span class="sxs-lookup"><span data-stu-id="82705-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82705-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82705-111">Requirements</span></span>  
 <span data-ttu-id="82705-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="82705-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82705-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82705-113">See Also</span></span>  
 [<span data-ttu-id="82705-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="82705-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="82705-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82705-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="82705-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82705-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
