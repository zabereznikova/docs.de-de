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
ms.openlocfilehash: aba551a1973a41a909869316cda07e8d655e9882
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614837"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="0f724-102">ISymUnmanagedWriter::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="0f724-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="0f724-103">Definiert eine einzelne Variable, die sich nicht innerhalb einer Methode befindet.</span><span class="sxs-lookup"><span data-stu-id="0f724-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="0f724-104">Diese Methode wird für bestimmte Felder in Klassen, Bitfeldern usw. verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f724-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f724-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f724-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0f724-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f724-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="0f724-107">in Der Metadatentyp oder das Methoden Token.</span><span class="sxs-lookup"><span data-stu-id="0f724-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="0f724-108">in Der Feldname.</span><span class="sxs-lookup"><span data-stu-id="0f724-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="0f724-109">in Die Feld Attribute.</span><span class="sxs-lookup"><span data-stu-id="0f724-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="0f724-110">in Ein mit `ULONG32` der Größe (in Zeichen) des Puffers, der die Feld Signatur enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="0f724-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="0f724-111">in Das Array von Feld Signaturen.</span><span class="sxs-lookup"><span data-stu-id="0f724-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="0f724-112">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="0f724-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="0f724-113">in Die erste Adresse für die Feld Angabe.</span><span class="sxs-lookup"><span data-stu-id="0f724-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="0f724-114">in Die zweite Adresse für die Feld Angabe.</span><span class="sxs-lookup"><span data-stu-id="0f724-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="0f724-115">in Die dritte Adresse für die Feld Angabe.</span><span class="sxs-lookup"><span data-stu-id="0f724-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f724-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f724-116">Return Value</span></span>  
 <span data-ttu-id="0f724-117">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0f724-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f724-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f724-118">Requirements</span></span>  
 <span data-ttu-id="0f724-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0f724-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f724-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f724-120">See also</span></span>

- [<span data-ttu-id="0f724-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f724-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
