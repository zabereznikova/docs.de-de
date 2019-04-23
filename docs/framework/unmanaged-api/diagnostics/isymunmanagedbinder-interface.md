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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105811"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="73e98-102">ISymUnmanagedBinder-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e98-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="73e98-103">Stellt einen Symbolbinder für nicht verwalteten Code dar.</span><span class="sxs-lookup"><span data-stu-id="73e98-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73e98-104">Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73e98-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73e98-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="73e98-105">Methods</span></span>  
  
|<span data-ttu-id="73e98-106">Methode</span><span class="sxs-lookup"><span data-stu-id="73e98-106">Method</span></span>|<span data-ttu-id="73e98-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73e98-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73e98-108">GetReaderForFile-Methode</span><span class="sxs-lookup"><span data-stu-id="73e98-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="73e98-109">Gibt bei Angabe einer Metadaten-Schnittstelle und einen Dateinamen ein, den richtigen [ISymUnmanagedReader](isymunmanagedreader-interface.md) Struktur, die die Debugsymbole, die dem Modul zugeordneten gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="73e98-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="73e98-110">GetReaderFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="73e98-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="73e98-111">Gibt bei Angabe einer Metadaten-Schnittstelle und ein Stream, der den Symbolspeicher enthält, die richtige [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur, die die Debugsymbole Symbole aus dem angegebenen Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="73e98-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73e98-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73e98-112">Requirements</span></span>  
 <span data-ttu-id="73e98-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="73e98-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e98-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73e98-114">See also</span></span>

- [<span data-ttu-id="73e98-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="73e98-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="73e98-116">ISymUnmanagedBinder2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e98-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="73e98-117">ISymUnmanagedBinder3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e98-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
