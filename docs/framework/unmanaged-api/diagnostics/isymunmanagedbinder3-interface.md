---
title: ISymUnmanagedBinder3-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157507"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="c9b2d-102">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9b2d-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="c9b2d-103">Erweitert die Symbol-Binder-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="c9b2d-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9b2d-105">Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9b2d-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="c9b2d-106">Methods</span></span>  
  
|<span data-ttu-id="c9b2d-107">Methode</span><span class="sxs-lookup"><span data-stu-id="c9b2d-107">Method</span></span>|<span data-ttu-id="c9b2d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9b2d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9b2d-109">GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="c9b2d-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="c9b2d-110">Ermöglicht dem Benutzer zu implementieren, oder geben Sie entweder über den Rückruf ein `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="c9b2d-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9b2d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9b2d-111">Requirements</span></span>  
 <span data-ttu-id="c9b2d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9b2d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9b2d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9b2d-113">See also</span></span>

- [<span data-ttu-id="c9b2d-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c9b2d-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c9b2d-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9b2d-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="c9b2d-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9b2d-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
