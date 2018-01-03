---
title: ISymUnmanagedVariable-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable
helpviewer_keywords: ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5ae8d1d05274363dc523c1a2cebf4ed09c1f461
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="8885f-102">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8885f-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="8885f-103">Stellt eine Variable, z. B. einen Parameter, eine lokale Variable oder ein Feld dar.</span><span class="sxs-lookup"><span data-stu-id="8885f-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8885f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8885f-104">Methods</span></span>  
  
|<span data-ttu-id="8885f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-105">Method</span></span>|<span data-ttu-id="8885f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8885f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8885f-107">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="8885f-108">Ruft das Feld für die erste Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="8885f-109">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="8885f-110">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="8885f-111">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="8885f-112">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="8885f-113">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="8885f-114">Ruft das Feld für die dritte Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="8885f-115">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="8885f-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="8885f-117">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="8885f-118">GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="8885f-119">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="8885f-120">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="8885f-121">Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="8885f-122">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="8885f-123">Ruft den Namen der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="8885f-124">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="8885f-125">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="8885f-126">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="8885f-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="8885f-127">Ruft den Anfangsoffset der Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="8885f-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8885f-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8885f-128">Requirements</span></span>  
 <span data-ttu-id="8885f-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8885f-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8885f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8885f-130">See Also</span></span>  
 [<span data-ttu-id="8885f-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8885f-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
