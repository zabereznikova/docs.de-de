---
title: ISymUnmanagedWriter::DefineField-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37794d40b4b379c5d3a05935cf1f2b7b3da11baa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777367"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="734fb-102">ISymUnmanagedWriter::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="734fb-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="734fb-103">Definiert eine einzelne Variable, die nicht innerhalb einer Methode ist.</span><span class="sxs-lookup"><span data-stu-id="734fb-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="734fb-104">Diese Methode ist für bestimmte Felder in Klassen, Bitfelder usw. verwendet.</span><span class="sxs-lookup"><span data-stu-id="734fb-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734fb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="734fb-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="734fb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="734fb-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="734fb-107">[in] Der Metadatentyp oder die Methode token.</span><span class="sxs-lookup"><span data-stu-id="734fb-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="734fb-108">[in] Der Name des Felds.</span><span class="sxs-lookup"><span data-stu-id="734fb-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="734fb-109">[in] Die Attribute des Felds.</span><span class="sxs-lookup"><span data-stu-id="734fb-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="734fb-110">[in] Ein `ULONG32` d. h. die Größe in Zeichen des Puffers erforderlich, um die Feldsignatur.</span><span class="sxs-lookup"><span data-stu-id="734fb-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="734fb-111">[in] Das Array von Feldsignaturen.</span><span class="sxs-lookup"><span data-stu-id="734fb-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="734fb-112">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="734fb-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="734fb-113">[in] Die erste Adresse für die Feldangabe.</span><span class="sxs-lookup"><span data-stu-id="734fb-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="734fb-114">[in] Die zweite Adresse für die Feldangabe.</span><span class="sxs-lookup"><span data-stu-id="734fb-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="734fb-115">[in] Die dritte Adresse für die Feldangabe.</span><span class="sxs-lookup"><span data-stu-id="734fb-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="734fb-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="734fb-116">Return Value</span></span>  
 <span data-ttu-id="734fb-117">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="734fb-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="734fb-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="734fb-118">Requirements</span></span>  
 <span data-ttu-id="734fb-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="734fb-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734fb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="734fb-120">See also</span></span>

- [<span data-ttu-id="734fb-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="734fb-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
