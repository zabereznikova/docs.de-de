---
title: ISymUnmanagedWriter::DefineGlobalVariable-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 674089f8a1076342a2479c64e253b7dda53ade87
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615201"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="e68a0-102">ISymUnmanagedWriter::DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="e68a0-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="e68a0-103">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="e68a0-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e68a0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e68a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e68a0-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e68a0-106">in Ein Zeiger auf einen `WCHAR` , der den Namen der globalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="e68a0-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="e68a0-107">in Die globalen Variablen Attribute.</span><span class="sxs-lookup"><span data-stu-id="e68a0-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e68a0-108">in Eine `ULONG32` , die die Größe des Puffers in Zeichen angibt `signature` .</span><span class="sxs-lookup"><span data-stu-id="e68a0-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="e68a0-109">in Die globale Variablen Signatur.</span><span class="sxs-lookup"><span data-stu-id="e68a0-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="e68a0-110">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="e68a0-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="e68a0-111">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="e68a0-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="e68a0-112">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="e68a0-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="e68a0-113">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="e68a0-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e68a0-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e68a0-114">Return Value</span></span>  
 <span data-ttu-id="e68a0-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="e68a0-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e68a0-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e68a0-116">Requirements</span></span>  
 <span data-ttu-id="e68a0-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e68a0-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68a0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e68a0-118">See also</span></span>

- [<span data-ttu-id="e68a0-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e68a0-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="e68a0-120">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="e68a0-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="e68a0-121">DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="e68a0-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
