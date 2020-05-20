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
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610170"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="a7364-102">ISymUnmanagedVariable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7364-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="a7364-103">Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.</span><span class="sxs-lookup"><span data-stu-id="a7364-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7364-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7364-104">Methods</span></span>  
  
|<span data-ttu-id="a7364-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-105">Method</span></span>|<span data-ttu-id="a7364-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7364-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7364-107">GetAddressField1-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="a7364-108">Ruft das erste Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="a7364-109">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a7364-110">GetAddressField2-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="a7364-111">Ruft das zweite Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="a7364-112">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a7364-113">GetAddressField3-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="a7364-114">Ruft das dritte Adressfeld für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="a7364-115">Ihre Bedeutung hängt von der Art der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="a7364-116">GetAddressKind-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="a7364-117">Ruft die Art der Adresse dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="a7364-118">GetAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="a7364-119">Ruft die Attributflags für diese Variable ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="a7364-120">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="a7364-121">Ruft den Endoffset dieser Variablen in ihrem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="a7364-122">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="a7364-123">Ruft den Namen dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="a7364-124">GetSignature-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="a7364-125">Ruft die Signatur dieser Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="a7364-126">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="a7364-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="a7364-127">Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab.</span><span class="sxs-lookup"><span data-stu-id="a7364-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7364-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7364-128">Requirements</span></span>  
 <span data-ttu-id="a7364-129">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="a7364-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7364-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7364-130">See also</span></span>

- [<span data-ttu-id="a7364-131">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7364-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
