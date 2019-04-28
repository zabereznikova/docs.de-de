---
title: ISymUnmanagedWriter::SetUserEntryPoint-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650725"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="a0ac6-102">ISymUnmanagedWriter::SetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="a0ac6-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="a0ac6-103">Gibt die benutzerdefinierte Methode, die der Einstiegspunkt für dieses Modul ist.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="a0ac6-104">Dieser Einstiegspunkt kann z. B. main-Methode des Benutzers statt vom Compiler generierten Stubs vor Main sein.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ac6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0ac6-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ac6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0ac6-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="a0ac6-107">[in] Zeigen Sie das Metadatentoken für die Methode, die der benutzerdefinierte Einstiegspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0ac6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0ac6-108">Return Value</span></span>  
 <span data-ttu-id="a0ac6-109">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a0ac6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ac6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0ac6-110">Requirements</span></span>  
 <span data-ttu-id="a0ac6-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a0ac6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ac6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0ac6-112">See also</span></span>

- [<span data-ttu-id="a0ac6-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0ac6-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
