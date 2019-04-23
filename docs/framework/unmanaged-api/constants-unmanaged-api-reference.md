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
ms.openlocfilehash: 8c76db644ffee478003d834460c155c4ec6d0070
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133951"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="660d0-102">Konstanten (nicht verwalteter API-Verweis)</span><span class="sxs-lookup"><span data-stu-id="660d0-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="660d0-103">Dieses Thema beschreibt die Sprachtyps Compilerhersteller und Dokument-Typ-Konstanten, die in CorSym.idl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="660d0-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="660d0-104">-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="660d0-104">Language Type Constants</span></span>  
 <span data-ttu-id="660d0-105">Die folgende Tabelle zeigt die Sprache Typkonstanten, die GUIDs darstellen, die Programmiersprachen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="660d0-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="660d0-106">Symbol</span><span class="sxs-lookup"><span data-stu-id="660d0-106">Symbol</span></span>|<span data-ttu-id="660d0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="660d0-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="660d0-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="660d0-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="660d0-109">Gibt die Programmiersprache C.</span><span class="sxs-lookup"><span data-stu-id="660d0-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="660d0-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="660d0-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="660d0-111">Gibt an, die Programmiersprache C++.</span><span class="sxs-lookup"><span data-stu-id="660d0-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="660d0-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="660d0-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="660d0-113">Gibt an, die C# Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="660d0-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="660d0-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="660d0-115">Gibt die Basic-Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="660d0-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="660d0-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="660d0-117">Gibt an, die Java-Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="660d0-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="660d0-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="660d0-119">Gibt die COBOL-Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="660d0-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="660d0-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="660d0-121">Gibt die Pascal-Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="660d0-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="660d0-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="660d0-123">Gibt an, die Microsoft intermediate Language (MSIL)-Assemblycode.</span><span class="sxs-lookup"><span data-stu-id="660d0-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="660d0-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="660d0-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="660d0-125">Gibt die Programmiersprache JScript an.</span><span class="sxs-lookup"><span data-stu-id="660d0-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="660d0-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="660d0-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="660d0-127">Gibt die SMC-Sprache.</span><span class="sxs-lookup"><span data-stu-id="660d0-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="660d0-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="660d0-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="660d0-129">Gibt die C++-Sprache, die für .NET Framework aktiviert.</span><span class="sxs-lookup"><span data-stu-id="660d0-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="660d0-130">Language-Anbieter-Konstanten</span><span class="sxs-lookup"><span data-stu-id="660d0-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="660d0-131">Die folgende Tabelle zeigt die Sprache Hersteller-Konstanten, die GUIDs darstellen, die Programmierung Compilerhersteller zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="660d0-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="660d0-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="660d0-132">Symbol</span></span>|<span data-ttu-id="660d0-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="660d0-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="660d0-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="660d0-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="660d0-135">Indicates Microsoft.</span><span class="sxs-lookup"><span data-stu-id="660d0-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="660d0-136">Dokument-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="660d0-136">Document Type Constants</span></span>  
 <span data-ttu-id="660d0-137">Die folgende Tabelle zeigt Dokument Typkonstanten, die GUIDs darstellen, die Typen von Dokumenten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="660d0-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="660d0-138">Symbol</span><span class="sxs-lookup"><span data-stu-id="660d0-138">Symbol</span></span>|<span data-ttu-id="660d0-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="660d0-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="660d0-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="660d0-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="660d0-141">Gibt an, ein Textdokument.</span><span class="sxs-lookup"><span data-stu-id="660d0-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="660d0-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="660d0-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="660d0-143">Gibt ein nicht-Text-Dokument an.</span><span class="sxs-lookup"><span data-stu-id="660d0-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="660d0-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="660d0-144">See also</span></span>

- [<span data-ttu-id="660d0-145">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="660d0-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
