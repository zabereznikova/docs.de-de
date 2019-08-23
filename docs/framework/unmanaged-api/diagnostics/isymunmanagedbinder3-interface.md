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
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944095"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="b82b8-102">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b82b8-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="b82b8-103">Erweitert die Symbol Binder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b82b8-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="b82b8-104">Rufen Sie diese Schnittstelle `QueryInterface` durch Aufrufen von für ein Objekt `ISymUnmanagedBinder` ab, das die-Schnittstelle implementiert</span><span class="sxs-lookup"><span data-stu-id="b82b8-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b82b8-105">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b82b8-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b82b8-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="b82b8-106">Methods</span></span>  
  
|<span data-ttu-id="b82b8-107">Methode</span><span class="sxs-lookup"><span data-stu-id="b82b8-107">Method</span></span>|<span data-ttu-id="b82b8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b82b8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b82b8-109">GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="b82b8-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="b82b8-110">Ermöglicht dem Benutzer das implementieren oder Bereitstellen von per Callback `IID_IDiaReadExeAtRVACallback` entweder `IID_IDiaReadExeAtOffsetCallback` oder, um die debugverzeichnisinformationen aus dem Arbeitsspeicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b82b8-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b82b8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b82b8-111">Requirements</span></span>  
 <span data-ttu-id="b82b8-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b82b8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82b8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b82b8-113">See also</span></span>

- [<span data-ttu-id="b82b8-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b82b8-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b82b8-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b82b8-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="b82b8-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b82b8-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
