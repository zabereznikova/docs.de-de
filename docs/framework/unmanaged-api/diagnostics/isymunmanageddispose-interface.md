---
title: ISymUnmanagedDispose-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 973fc35bb99bea6b3302760763069b9df6c548e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424403"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="40e9e-102">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40e9e-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="40e9e-103">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="40e9e-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40e9e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="40e9e-104">Methods</span></span>  
  
|<span data-ttu-id="40e9e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="40e9e-105">Method</span></span>|<span data-ttu-id="40e9e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40e9e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40e9e-107">Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="40e9e-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="40e9e-108">Bewirkt, dass das zugrunde liegende Objekt alle internen Verweise freigeben und Fehler für alle nachfolgenden Methodenaufrufe zurück.</span><span class="sxs-lookup"><span data-stu-id="40e9e-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40e9e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e9e-109">Requirements</span></span>  
 <span data-ttu-id="40e9e-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="40e9e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e9e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40e9e-111">See Also</span></span>  
 [<span data-ttu-id="40e9e-112">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="40e9e-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
