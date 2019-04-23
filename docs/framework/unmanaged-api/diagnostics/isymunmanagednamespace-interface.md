---
title: ISymUnmanagedNamespace-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace
helpviewer_keywords:
- ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87dd6db9624c2216ab13e77b04cfa63f95aee7e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183312"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="ebcbe-102">ISymUnmanagedNamespace-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebcbe-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="ebcbe-103">Stellt einen Namespace dar.</span><span class="sxs-lookup"><span data-stu-id="ebcbe-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ebcbe-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ebcbe-104">Methods</span></span>  
  
|<span data-ttu-id="ebcbe-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ebcbe-105">Method</span></span>|<span data-ttu-id="ebcbe-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ebcbe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ebcbe-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ebcbe-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="ebcbe-108">Ruft den Namen des Namespace.</span><span class="sxs-lookup"><span data-stu-id="ebcbe-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="ebcbe-109">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="ebcbe-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="ebcbe-110">Ruft die untergeordneten Elemente dieses Namespaces ab.</span><span class="sxs-lookup"><span data-stu-id="ebcbe-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="ebcbe-111">GetVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="ebcbe-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="ebcbe-112">Gibt alle Variablen, die im globalen Gültigkeitsbereich innerhalb dieses Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="ebcbe-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebcbe-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ebcbe-113">Requirements</span></span>  
 <span data-ttu-id="ebcbe-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ebcbe-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcbe-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebcbe-115">See also</span></span>

- [<span data-ttu-id="ebcbe-116">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ebcbe-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
