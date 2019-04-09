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
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164345"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="68d84-102">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68d84-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="68d84-103">Stellt eine Variable ein, z. B. ein Parameter, eine lokale Variable oder ein Feld dar.</span><span class="sxs-lookup"><span data-stu-id="68d84-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68d84-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="68d84-104">Methods</span></span>  
  
|<span data-ttu-id="68d84-105">Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-105">Method</span></span>|<span data-ttu-id="68d84-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68d84-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68d84-107">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="68d84-108">Ruft das erste Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="68d84-109">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="68d84-110">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="68d84-111">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="68d84-112">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="68d84-113">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="68d84-114">Ruft das dritte Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="68d84-115">Die Bedeutung, hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="68d84-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="68d84-117">Ruft die Art der Adresse dieser Variablen.</span><span class="sxs-lookup"><span data-stu-id="68d84-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="68d84-118">GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="68d84-119">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="68d84-120">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="68d84-121">Ruft den Endoffset des dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="68d84-122">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="68d84-123">Ruft den Namen dieser Variablen.</span><span class="sxs-lookup"><span data-stu-id="68d84-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="68d84-124">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="68d84-125">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="68d84-126">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="68d84-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="68d84-127">Ruft den Anfangsoffset dieser Variablen in seinem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="68d84-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68d84-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68d84-128">Requirements</span></span>  
 <span data-ttu-id="68d84-129">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="68d84-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68d84-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68d84-130">See also</span></span>

- [<span data-ttu-id="68d84-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68d84-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
