---
title: ISymUnmanagedWriter::CloseMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
ms.openlocfilehash: a6a6aa937078ed0627688a4eed3d9142a2e6e0ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428106"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="62220-102">ISymUnmanagedWriter::CloseMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="62220-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="62220-103">Schließt die aktuelle Methode.</span><span class="sxs-lookup"><span data-stu-id="62220-103">Closes the current method.</span></span> <span data-ttu-id="62220-104">Nachdem eine Methode geschlossen wurde, können darin keine weiteren Symbole definiert werden.</span><span class="sxs-lookup"><span data-stu-id="62220-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62220-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="62220-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="62220-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62220-106">Return Value</span></span>  
 <span data-ttu-id="62220-107">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="62220-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62220-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="62220-108">Requirements</span></span>  
 <span data-ttu-id="62220-109">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="62220-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62220-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62220-110">See also</span></span>

- [<span data-ttu-id="62220-111">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62220-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="62220-112">OpenMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="62220-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
