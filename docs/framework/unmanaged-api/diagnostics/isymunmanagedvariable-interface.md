---
title: ISymUnmanagedVariable-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3db4fc691637c049e0374416cb92a2056555ad11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428699"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="91268-102">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91268-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="91268-103">Stellt eine Variable, z. B. einen Parameter, eine lokale Variable oder ein Feld dar.</span><span class="sxs-lookup"><span data-stu-id="91268-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91268-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="91268-104">Methods</span></span>  
  
|<span data-ttu-id="91268-105">Methode</span><span class="sxs-lookup"><span data-stu-id="91268-105">Method</span></span>|<span data-ttu-id="91268-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91268-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91268-107">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="91268-108">Ruft das Feld für die erste Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="91268-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="91268-109">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="91268-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="91268-110">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="91268-111">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="91268-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="91268-112">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="91268-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="91268-113">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="91268-114">Ruft das Feld für die dritte Adresse für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="91268-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="91268-115">Seiner Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="91268-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="91268-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="91268-117">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="91268-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="91268-118">GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="91268-119">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="91268-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="91268-120">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="91268-121">Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="91268-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="91268-122">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="91268-123">Ruft den Namen der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="91268-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="91268-124">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="91268-125">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="91268-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="91268-126">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="91268-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="91268-127">Ruft den Anfangsoffset der Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="91268-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91268-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91268-128">Requirements</span></span>  
 <span data-ttu-id="91268-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91268-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91268-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91268-130">See Also</span></span>  
 [<span data-ttu-id="91268-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91268-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
