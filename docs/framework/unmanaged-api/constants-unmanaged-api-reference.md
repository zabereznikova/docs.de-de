---
title: Konstanten (nicht verwalteter API-Verweis)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45e4d41c16695010dc452d2f22850d43f885974a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="de089-102">Konstanten (nicht verwalteter API-Verweis)</span><span class="sxs-lookup"><span data-stu-id="de089-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="de089-103">Dieses Thema beschreibt die Language-Typ, Compilerhersteller und Dokumenttypkonstanten, die in CorSym.idl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="de089-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="de089-104">Language-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="de089-104">Language Type Constants</span></span>  
 <span data-ttu-id="de089-105">Die folgende Tabelle zeigt die Sprache Konstanten, die GUIDs darstellen, die Programmiersprachen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="de089-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="de089-106">Symbol</span><span class="sxs-lookup"><span data-stu-id="de089-106">Symbol</span></span>|<span data-ttu-id="de089-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de089-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de089-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="de089-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="de089-109">Gibt die Programmiersprache C.</span><span class="sxs-lookup"><span data-stu-id="de089-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="de089-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="de089-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="de089-111">Gibt die Programmiersprache C++ an.</span><span class="sxs-lookup"><span data-stu-id="de089-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="de089-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="de089-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="de089-113">Gibt die C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="de089-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="de089-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="de089-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="de089-115">Gibt die grundlegende Sprache.</span><span class="sxs-lookup"><span data-stu-id="de089-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="de089-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="de089-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="de089-117">Gibt die Programmiersprache an.</span><span class="sxs-lookup"><span data-stu-id="de089-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="de089-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="de089-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="de089-119">Gibt die COBOL-Sprache.</span><span class="sxs-lookup"><span data-stu-id="de089-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="de089-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="de089-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="de089-121">Gibt die Pascal-Sprache.</span><span class="sxs-lookup"><span data-stu-id="de089-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="de089-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="de089-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="de089-123">Gibt an, die Microsoft intermediate Language (MSIL)-Assemblycode.</span><span class="sxs-lookup"><span data-stu-id="de089-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="de089-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="de089-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="de089-125">Gibt die JScript-Sprache.</span><span class="sxs-lookup"><span data-stu-id="de089-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="de089-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="de089-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="de089-127">Gibt die Programmiersprache SMC an.</span><span class="sxs-lookup"><span data-stu-id="de089-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="de089-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="de089-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="de089-129">Gibt die C++-Sprache, die für .NET Framework aktiviert.</span><span class="sxs-lookup"><span data-stu-id="de089-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="de089-130">Language-Hersteller-Konstanten</span><span class="sxs-lookup"><span data-stu-id="de089-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="de089-131">Die folgende Tabelle zeigt die Sprache Hersteller-Konstanten, die GUIDs darstellen, die programming Language Lieferanten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="de089-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="de089-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="de089-132">Symbol</span></span>|<span data-ttu-id="de089-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de089-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de089-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="de089-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="de089-135">Gibt an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de089-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="de089-136">Dokument-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="de089-136">Document Type Constants</span></span>  
 <span data-ttu-id="de089-137">Die folgende Tabelle zeigt Dokument Konstanten, die GUIDs darstellen, die Dokumenttypen identifizieren.</span><span class="sxs-lookup"><span data-stu-id="de089-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="de089-138">Symbol</span><span class="sxs-lookup"><span data-stu-id="de089-138">Symbol</span></span>|<span data-ttu-id="de089-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de089-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="de089-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="de089-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="de089-141">Gibt ein Textdokument an.</span><span class="sxs-lookup"><span data-stu-id="de089-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="de089-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="de089-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="de089-143">Gibt ein Textdokument an.</span><span class="sxs-lookup"><span data-stu-id="de089-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de089-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de089-144">See Also</span></span>  
 [<span data-ttu-id="de089-145">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="de089-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
