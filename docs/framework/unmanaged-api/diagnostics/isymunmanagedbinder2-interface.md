---
title: ISymUnmanagedBinder2-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38de9fa878db18222d2666ba86420ca856e4b121
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199114"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="ff9ea-102">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff9ea-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="ff9ea-103">Stellt einen Symbolbinder für nicht verwalteten Code dar, und erweitert die [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ff9ea-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff9ea-104">Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ff9ea-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff9ea-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff9ea-105">Methods</span></span>  
  
|<span data-ttu-id="ff9ea-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ff9ea-106">Method</span></span>|<span data-ttu-id="ff9ea-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff9ea-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff9ea-108">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="ff9ea-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="ff9ea-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) Schnittstelle, die die Debugsymbole, die dem Modul zugeordneten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="ff9ea-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="ff9ea-110">Bietet eine ausführliche Suche als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ff9ea-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff9ea-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff9ea-111">Requirements</span></span>  
 <span data-ttu-id="ff9ea-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff9ea-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9ea-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff9ea-113">See also</span></span>

- [<span data-ttu-id="ff9ea-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff9ea-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ff9ea-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff9ea-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="ff9ea-116">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff9ea-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
