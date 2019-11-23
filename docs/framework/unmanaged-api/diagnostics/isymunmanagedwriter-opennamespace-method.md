---
title: ISymUnmanagedWriter::OpenNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: acbd49de7362d9c05a609a2d870af100637e10ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427907"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="d7489-102">ISymUnmanagedWriter::OpenNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="d7489-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="d7489-103">Öffnet einen neuen Namespace.</span><span class="sxs-lookup"><span data-stu-id="d7489-103">Opens a new namespace.</span></span> <span data-ttu-id="d7489-104">Call this method before defining methods or variables that occupy a namespace.</span><span class="sxs-lookup"><span data-stu-id="d7489-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="d7489-105">Namespaces can be nested.</span><span class="sxs-lookup"><span data-stu-id="d7489-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7489-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7489-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7489-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7489-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d7489-108">[in] A pointer to the name of the new namespace.</span><span class="sxs-lookup"><span data-stu-id="d7489-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7489-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7489-109">Return Value</span></span>  
 <span data-ttu-id="d7489-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="d7489-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7489-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7489-111">Requirements</span></span>  
 <span data-ttu-id="d7489-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7489-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7489-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7489-113">See also</span></span>

- [<span data-ttu-id="d7489-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7489-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d7489-115">CloseNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="d7489-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
