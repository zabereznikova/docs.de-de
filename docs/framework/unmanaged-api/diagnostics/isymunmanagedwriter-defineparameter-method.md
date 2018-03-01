---
title: ISymUnmanagedWriter::DefineParameter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7fe62a8f6b48d1a9931cc0310811d7fc42f7029b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="13e2a-102">ISymUnmanagedWriter::DefineParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="13e2a-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="13e2a-103">Definiert einen einzelnen Parameter in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="13e2a-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="13e2a-104">Der Parametertyp stammt von der Position des Parameters (Sequenz) in der Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="13e2a-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="13e2a-105">Wenn in den Metadaten für eine bestimmte Methode Parameter definiert sind, müssen Sie nicht erneut mit dieser Methode definieren.</span><span class="sxs-lookup"><span data-stu-id="13e2a-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="13e2a-106">Die Symbolreader müssen die normale Metadaten für die Parameter überprüfen, bevor Sie den Symbolspeicher überprüfen.</span><span class="sxs-lookup"><span data-stu-id="13e2a-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e2a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="13e2a-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13e2a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="13e2a-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="13e2a-109">[in] Der Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="13e2a-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="13e2a-110">[in] Die Parameterattribute.</span><span class="sxs-lookup"><span data-stu-id="13e2a-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="13e2a-111">[in] Die Parametersignatur.</span><span class="sxs-lookup"><span data-stu-id="13e2a-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="13e2a-112">[in] Der Adresstyp.</span><span class="sxs-lookup"><span data-stu-id="13e2a-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="13e2a-113">[in] Die erste Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="13e2a-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="13e2a-114">[in] Die zweite Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="13e2a-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="13e2a-115">[in] Die dritte Adresse für die Parameterspezifikation.</span><span class="sxs-lookup"><span data-stu-id="13e2a-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13e2a-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="13e2a-116">Return Value</span></span>  
 <span data-ttu-id="13e2a-117">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="13e2a-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e2a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13e2a-118">Requirements</span></span>  
 <span data-ttu-id="13e2a-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13e2a-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e2a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13e2a-120">See Also</span></span>  
 [<span data-ttu-id="13e2a-121">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13e2a-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
