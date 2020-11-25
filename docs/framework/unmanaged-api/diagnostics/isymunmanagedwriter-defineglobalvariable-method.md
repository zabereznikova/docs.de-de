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
ms.openlocfilehash: bc389b7247a6b1d6ce16cb3cf350f1672213b2e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716420"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="21209-102">ISymUnmanagedWriter::DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="21209-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>

<span data-ttu-id="21209-103">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="21209-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21209-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21209-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="21209-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21209-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="21209-106">in Ein Zeiger auf einen `WCHAR` , der den Namen der globalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="21209-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="21209-107">in Die globalen Variablen Attribute.</span><span class="sxs-lookup"><span data-stu-id="21209-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="21209-108">in Eine `ULONG32` , die die Größe des Puffers in Zeichen angibt `signature` .</span><span class="sxs-lookup"><span data-stu-id="21209-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="21209-109">in Die globale Variablen Signatur.</span><span class="sxs-lookup"><span data-stu-id="21209-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="21209-110">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="21209-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="21209-111">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="21209-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="21209-112">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="21209-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="21209-113">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="21209-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21209-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21209-114">Return Value</span></span>  

 <span data-ttu-id="21209-115">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="21209-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21209-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21209-116">Requirements</span></span>  

 <span data-ttu-id="21209-117">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="21209-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21209-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21209-118">See also</span></span>

- [<span data-ttu-id="21209-119">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21209-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="21209-120">DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="21209-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="21209-121">DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="21209-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
