---
title: ISymUnmanagedWriter::DefineParameter-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
ms.openlocfilehash: c5e36443295395997303cb94202f534a83d086f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677868"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="0b379-102">ISymUnmanagedWriter::DefineParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="0b379-102">ISymUnmanagedWriter::DefineParameter Method</span></span>

<span data-ttu-id="0b379-103">Definiert einen einzelnen Parameter in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="0b379-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="0b379-104">Der Parametertyp wird aus der Position (Sequence) des Parameters innerhalb der Signatur der Methode entnommen.</span><span class="sxs-lookup"><span data-stu-id="0b379-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="0b379-105">Wenn Parameter in den Metadaten für eine bestimmte Methode definiert sind, müssen Sie Sie nicht mit dieser Methode erneut definieren.</span><span class="sxs-lookup"><span data-stu-id="0b379-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="0b379-106">Die Symbol Leser müssen die normalen Metadaten für die Parameter überprüfen, bevor Sie den Symbol Speicher überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0b379-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b379-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b379-107">Syntax</span></span>  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b379-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b379-108">Parameters</span></span>  

 `name`  
 <span data-ttu-id="0b379-109">in Der Parameter Name.</span><span class="sxs-lookup"><span data-stu-id="0b379-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="0b379-110">in Die Parameter Attribute.</span><span class="sxs-lookup"><span data-stu-id="0b379-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="0b379-111">in Die Parameter Signatur.</span><span class="sxs-lookup"><span data-stu-id="0b379-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="0b379-112">in Der adrestyp.</span><span class="sxs-lookup"><span data-stu-id="0b379-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="0b379-113">in Die erste Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="0b379-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="0b379-114">in Die zweite Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="0b379-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="0b379-115">in Die dritte Adresse für die Parameter Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="0b379-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b379-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b379-116">Return Value</span></span>  

 <span data-ttu-id="0b379-117">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="0b379-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b379-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b379-118">Requirements</span></span>  

 <span data-ttu-id="0b379-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0b379-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b379-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b379-120">See also</span></span>

- [<span data-ttu-id="0b379-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b379-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
