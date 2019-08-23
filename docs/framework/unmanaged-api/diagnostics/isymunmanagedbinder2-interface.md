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
ms.openlocfilehash: c9fbb8364fb967e739eb9807b26cbc65f0ebec1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944194"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="e83ff-102">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e83ff-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="e83ff-103">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e83ff-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e83ff-104">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e83ff-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e83ff-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e83ff-105">Methods</span></span>  
  
|<span data-ttu-id="e83ff-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e83ff-106">Method</span></span>|<span data-ttu-id="e83ff-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e83ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e83ff-108">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="e83ff-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="e83ff-109">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="e83ff-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="e83ff-110">Bietet eine umfassendere Suche als die [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="e83ff-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e83ff-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e83ff-111">Requirements</span></span>  
 <span data-ttu-id="e83ff-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e83ff-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83ff-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e83ff-113">See also</span></span>

- [<span data-ttu-id="e83ff-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e83ff-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e83ff-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e83ff-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="e83ff-116">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e83ff-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
