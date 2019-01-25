---
title: Konstanten (nicht verwalteter API-Verweis)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c537e4967c284df899a131b44d96dbdb6e1af29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587673"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="ca87e-102">Konstanten (nicht verwalteter API-Verweis)</span><span class="sxs-lookup"><span data-stu-id="ca87e-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="ca87e-103">Dieses Thema beschreibt die Sprachtyps Compilerhersteller und Dokument-Typ-Konstanten, die in CorSym.idl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ca87e-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="ca87e-104">-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="ca87e-104">Language Type Constants</span></span>  
 <span data-ttu-id="ca87e-105">Die folgende Tabelle zeigt die Sprache Typkonstanten, die GUIDs darstellen, die Programmiersprachen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ca87e-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="ca87e-106">Symbol</span><span class="sxs-lookup"><span data-stu-id="ca87e-106">Symbol</span></span>|<span data-ttu-id="ca87e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca87e-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ca87e-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="ca87e-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="ca87e-109">Gibt die Programmiersprache C.</span><span class="sxs-lookup"><span data-stu-id="ca87e-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="ca87e-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="ca87e-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="ca87e-111">Gibt an, die Programmiersprache C++.</span><span class="sxs-lookup"><span data-stu-id="ca87e-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="ca87e-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="ca87e-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="ca87e-113">Gibt an, die C# Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="ca87e-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="ca87e-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="ca87e-115">Gibt die Basic-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="ca87e-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="ca87e-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="ca87e-117">Gibt an, die Java-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="ca87e-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="ca87e-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="ca87e-119">Gibt die COBOL-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="ca87e-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="ca87e-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="ca87e-121">Gibt die Pascal-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="ca87e-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="ca87e-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="ca87e-123">Gibt an, die Microsoft intermediate Language (MSIL)-Assemblycode.</span><span class="sxs-lookup"><span data-stu-id="ca87e-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="ca87e-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="ca87e-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="ca87e-125">Gibt die Programmiersprache JScript an.</span><span class="sxs-lookup"><span data-stu-id="ca87e-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="ca87e-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="ca87e-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="ca87e-127">Gibt die SMC-Sprache.</span><span class="sxs-lookup"><span data-stu-id="ca87e-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="ca87e-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="ca87e-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="ca87e-129">Gibt die C++-Sprache, die für .NET Framework aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca87e-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="ca87e-130">Language-Anbieter-Konstanten</span><span class="sxs-lookup"><span data-stu-id="ca87e-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="ca87e-131">Die folgende Tabelle zeigt die Sprache Hersteller-Konstanten, die GUIDs darstellen, die Programmierung Compilerhersteller zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ca87e-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="ca87e-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="ca87e-132">Symbol</span></span>|<span data-ttu-id="ca87e-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca87e-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ca87e-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca87e-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="ca87e-135">Indicates Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ca87e-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="ca87e-136">Dokument-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="ca87e-136">Document Type Constants</span></span>  
 <span data-ttu-id="ca87e-137">Die folgende Tabelle zeigt Dokument Typkonstanten, die GUIDs darstellen, die Typen von Dokumenten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ca87e-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="ca87e-138">Symbol</span><span class="sxs-lookup"><span data-stu-id="ca87e-138">Symbol</span></span>|<span data-ttu-id="ca87e-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca87e-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ca87e-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="ca87e-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="ca87e-141">Gibt an, ein Textdokument.</span><span class="sxs-lookup"><span data-stu-id="ca87e-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="ca87e-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="ca87e-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="ca87e-143">Gibt ein nicht-Text-Dokument an.</span><span class="sxs-lookup"><span data-stu-id="ca87e-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca87e-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca87e-144">See also</span></span>
- [<span data-ttu-id="ca87e-145">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="ca87e-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
