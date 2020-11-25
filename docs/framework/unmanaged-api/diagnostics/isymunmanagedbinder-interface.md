---
title: ISymUnmanagedBinder-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: 554e59484f00626726f7f024c69e93a5e6647130
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727379"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="a9736-102">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9736-102">ISymUnmanagedBinder Interface</span></span>

<span data-ttu-id="a9736-103">Stellt einen Symbolbinder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="a9736-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a9736-104">Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a9736-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9736-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a9736-105">Methods</span></span>  
  
|<span data-ttu-id="a9736-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a9736-106">Method</span></span>|<span data-ttu-id="a9736-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a9736-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9736-108">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="a9736-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="a9736-109">Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die dem Modul zugeordneten Debugsymbole liest.</span><span class="sxs-lookup"><span data-stu-id="a9736-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="a9736-110">GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="a9736-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="a9736-111">Gibt bei einer Metadatenschnittstelle und einem Stream, der den Symbol Speicher enthält, die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die Debugsymbole aus dem angegebenen Symbol Speicher liest.</span><span class="sxs-lookup"><span data-stu-id="a9736-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9736-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a9736-112">Requirements</span></span>  

 <span data-ttu-id="a9736-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a9736-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9736-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9736-114">See also</span></span>

- [<span data-ttu-id="a9736-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a9736-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a9736-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9736-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="a9736-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9736-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
