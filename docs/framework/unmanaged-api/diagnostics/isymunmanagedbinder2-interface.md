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
ms.openlocfilehash: f6155eb777b5071ff522af4f27d5fb2d73aa25ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501832"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="b9427-102">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9427-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="b9427-103">Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b9427-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b9427-104">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b9427-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9427-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b9427-105">Methods</span></span>  
  
|<span data-ttu-id="b9427-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b9427-106">Method</span></span>|<span data-ttu-id="b9427-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b9427-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9427-108">GetReaderForFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="b9427-108">GetReaderForFile2 Method</span></span>](isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="b9427-109">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="b9427-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="b9427-110">Bietet eine umfassendere Suche als die [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="b9427-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9427-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b9427-111">Requirements</span></span>  
 <span data-ttu-id="b9427-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b9427-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9427-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b9427-113">See also</span></span>

- [<span data-ttu-id="b9427-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b9427-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b9427-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9427-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="b9427-116">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9427-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
