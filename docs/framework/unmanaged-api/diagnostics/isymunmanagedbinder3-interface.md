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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939996"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="c2b4c-102">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2b4c-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="c2b4c-103">Erweitert die Symbol-Binder-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2b4c-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="c2b4c-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die `ISymUnmanagedBinder` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c2b4c-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c2b4c-105">Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c2b4c-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2b4c-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="c2b4c-106">Methods</span></span>  
  
|<span data-ttu-id="c2b4c-107">Methode</span><span class="sxs-lookup"><span data-stu-id="c2b4c-107">Method</span></span>|<span data-ttu-id="c2b4c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2b4c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2b4c-109">GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="c2b4c-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="c2b4c-110">Ermöglicht dem Benutzer zu implementieren, oder geben Sie entweder über den Rückruf ein `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="c2b4c-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2b4c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2b4c-111">Requirements</span></span>  
 <span data-ttu-id="c2b4c-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c2b4c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b4c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2b4c-113">See also</span></span>

- [<span data-ttu-id="c2b4c-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2b4c-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c2b4c-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2b4c-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="c2b4c-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2b4c-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
