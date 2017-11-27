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
ms.openlocfilehash: c32d5b66c575a21b4d390cff560b71f93aa31927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="ddd58-102">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddd58-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="ddd58-103">Stellt eine Variable, z. B. einen Parameter, eine lokale Variable oder ein Feld dar.</span><span class="sxs-lookup"><span data-stu-id="ddd58-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddd58-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ddd58-104">Methods</span></span>  
  
|<span data-ttu-id="ddd58-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-105">Method</span></span>|<span data-ttu-id="ddd58-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddd58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddd58-107">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="ddd58-108">Ruft das Feld für die erste Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="ddd58-109">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ddd58-110">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="ddd58-111">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="ddd58-112">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ddd58-113">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="ddd58-114">Ruft das Feld für die dritte Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="ddd58-115">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="ddd58-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="ddd58-117">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="ddd58-118">GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="ddd58-119">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="ddd58-120">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="ddd58-121">Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="ddd58-122">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="ddd58-123">Ruft den Namen der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="ddd58-124">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="ddd58-125">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="ddd58-126">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="ddd58-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="ddd58-127">Ruft den Anfangsoffset der Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="ddd58-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddd58-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ddd58-128">Requirements</span></span>  
 <span data-ttu-id="ddd58-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ddd58-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd58-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddd58-130">See Also</span></span>  
 [<span data-ttu-id="ddd58-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ddd58-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
