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
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727314"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="6e71a-102">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e71a-102">ISymUnmanagedBinder3 Interface</span></span>

<span data-ttu-id="6e71a-103">Erweitert die Symbol Binder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6e71a-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="6e71a-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die- `ISymUnmanagedBinder` Schnittstelle implementiert</span><span class="sxs-lookup"><span data-stu-id="6e71a-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6e71a-105">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6e71a-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e71a-106">Methoden</span><span class="sxs-lookup"><span data-stu-id="6e71a-106">Methods</span></span>  
  
|<span data-ttu-id="6e71a-107">Methode</span><span class="sxs-lookup"><span data-stu-id="6e71a-107">Method</span></span>|<span data-ttu-id="6e71a-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6e71a-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e71a-109">GetReaderFromCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="6e71a-109">GetReaderFromCallback Method</span></span>](isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="6e71a-110">Ermöglicht dem Benutzer das implementieren oder Bereitstellen von per Callback entweder `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` , um die debugverzeichnisinformationen aus dem Arbeitsspeicher zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e71a-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e71a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e71a-111">Requirements</span></span>  

 <span data-ttu-id="6e71a-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="6e71a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e71a-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e71a-113">See also</span></span>

- [<span data-ttu-id="6e71a-114">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6e71a-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6e71a-115">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e71a-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="6e71a-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e71a-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
