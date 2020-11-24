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
ms.openlocfilehash: a1c3506758221c3a2b578d93488a4377c1b86a21
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683497"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="0d17b-102">ISymUnmanagedWriter::SetUserEntryPoint-Methode</span><span class="sxs-lookup"><span data-stu-id="0d17b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>

<span data-ttu-id="0d17b-103">Gibt die benutzerdefinierte Methode an, die der Einstiegspunkt für dieses Modul ist.</span><span class="sxs-lookup"><span data-stu-id="0d17b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="0d17b-104">Dieser Einstiegspunkt kann z. b. die Hauptmethode des Benutzers anstelle der vom Compiler generierten Stub vor "Main" sein.</span><span class="sxs-lookup"><span data-stu-id="0d17b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d17b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d17b-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d17b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d17b-106">Parameters</span></span>  

 `entryMethod`  
 <span data-ttu-id="0d17b-107">in Das Metadatentoken für die Methode, die der Benutzer Einstiegspunkt ist.</span><span class="sxs-lookup"><span data-stu-id="0d17b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d17b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d17b-108">Return Value</span></span>  

 <span data-ttu-id="0d17b-109">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0d17b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d17b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0d17b-110">Requirements</span></span>  

 <span data-ttu-id="0d17b-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0d17b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d17b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d17b-112">See also</span></span>

- [<span data-ttu-id="0d17b-113">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d17b-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
