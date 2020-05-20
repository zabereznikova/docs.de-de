---
title: ISymUnmanagedWriter::DefineLocalVariable-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614824"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="dde78-102">ISymUnmanagedWriter::DefineLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="dde78-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="dde78-103">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="dde78-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="dde78-104">Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt.</span><span class="sxs-lookup"><span data-stu-id="dde78-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="dde78-105">In diesem Fall dürfen sich die Werte des `startOffset` -Parameters und des- `endOffset` Parameters jedoch nicht überlappen.</span><span class="sxs-lookup"><span data-stu-id="dde78-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde78-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dde78-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dde78-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="dde78-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="dde78-108">in Ein Zeiger auf einen `WCHAR` , der den Namen der lokalen Variablen definiert.</span><span class="sxs-lookup"><span data-stu-id="dde78-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="dde78-109">in Die Attribute der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="dde78-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="dde78-110">in Eine `ULONG32` , die die Größe des Puffers in Bytes angibt `signature` .</span><span class="sxs-lookup"><span data-stu-id="dde78-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="dde78-111">in Die Signatur der lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="dde78-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="dde78-112">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="dde78-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="dde78-113">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="dde78-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="dde78-114">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="dde78-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="dde78-115">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="dde78-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="dde78-116">in Der Anfangs Offset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="dde78-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="dde78-117">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="dde78-117">This parameter is optional.</span></span> <span data-ttu-id="dde78-118">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="dde78-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="dde78-119">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="dde78-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="dde78-120">in Der Endoffset für die Variable.</span><span class="sxs-lookup"><span data-stu-id="dde78-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="dde78-121">Dieser Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="dde78-121">This parameter is optional.</span></span> <span data-ttu-id="dde78-122">Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="dde78-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="dde78-123">Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.</span><span class="sxs-lookup"><span data-stu-id="dde78-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dde78-124">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dde78-124">Return Value</span></span>  
 <span data-ttu-id="dde78-125">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="dde78-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dde78-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dde78-126">Requirements</span></span>  
 <span data-ttu-id="dde78-127">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="dde78-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde78-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dde78-128">See also</span></span>

- [<span data-ttu-id="dde78-129">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dde78-129">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="dde78-130">DefineGlobalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="dde78-130">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="dde78-131">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="dde78-131">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
