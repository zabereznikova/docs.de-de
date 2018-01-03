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
ms.workload: dotnet
ms.openlocfilehash: e086e856bb7a872b14815825f78d208ff5296899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="2b502-102">Konstanten (nicht verwalteter API-Verweis)</span><span class="sxs-lookup"><span data-stu-id="2b502-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="2b502-103">Dieses Thema beschreibt die Language-Typ, Compilerhersteller und Dokumenttypkonstanten, die in CorSym.idl definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2b502-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="2b502-104">Language-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="2b502-104">Language Type Constants</span></span>  
 <span data-ttu-id="2b502-105">Die folgende Tabelle zeigt die Sprache Konstanten, die GUIDs darstellen, die Programmiersprachen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b502-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="2b502-106">Symbol</span><span class="sxs-lookup"><span data-stu-id="2b502-106">Symbol</span></span>|<span data-ttu-id="2b502-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b502-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b502-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="2b502-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="2b502-109">Gibt die Programmiersprache C.</span><span class="sxs-lookup"><span data-stu-id="2b502-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="2b502-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="2b502-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="2b502-111">Gibt die Programmiersprache C++ an.</span><span class="sxs-lookup"><span data-stu-id="2b502-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="2b502-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="2b502-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="2b502-113">Gibt die C#-Sprache.</span><span class="sxs-lookup"><span data-stu-id="2b502-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="2b502-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="2b502-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="2b502-115">Gibt die grundlegende Sprache.</span><span class="sxs-lookup"><span data-stu-id="2b502-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="2b502-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="2b502-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="2b502-117">Gibt die Programmiersprache an.</span><span class="sxs-lookup"><span data-stu-id="2b502-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="2b502-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="2b502-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="2b502-119">Gibt die COBOL-Sprache.</span><span class="sxs-lookup"><span data-stu-id="2b502-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="2b502-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="2b502-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="2b502-121">Gibt die Pascal-Sprache.</span><span class="sxs-lookup"><span data-stu-id="2b502-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="2b502-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="2b502-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="2b502-123">Gibt an, die Microsoft intermediate Language (MSIL)-Assemblycode.</span><span class="sxs-lookup"><span data-stu-id="2b502-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="2b502-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="2b502-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="2b502-125">Gibt die JScript-Sprache.</span><span class="sxs-lookup"><span data-stu-id="2b502-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="2b502-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="2b502-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="2b502-127">Gibt die Programmiersprache SMC an.</span><span class="sxs-lookup"><span data-stu-id="2b502-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="2b502-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="2b502-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="2b502-129">Gibt die C++-Sprache, die für .NET Framework aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b502-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="2b502-130">Language-Hersteller-Konstanten</span><span class="sxs-lookup"><span data-stu-id="2b502-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="2b502-131">Die folgende Tabelle zeigt die Sprache Hersteller-Konstanten, die GUIDs darstellen, die programming Language Lieferanten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b502-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="2b502-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="2b502-132">Symbol</span></span>|<span data-ttu-id="2b502-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b502-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b502-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b502-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="2b502-135">Gibt an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b502-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="2b502-136">Dokument-Typ-Konstanten</span><span class="sxs-lookup"><span data-stu-id="2b502-136">Document Type Constants</span></span>  
 <span data-ttu-id="2b502-137">Die folgende Tabelle zeigt Dokument Konstanten, die GUIDs darstellen, die Dokumenttypen identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2b502-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="2b502-138">Symbol</span><span class="sxs-lookup"><span data-stu-id="2b502-138">Symbol</span></span>|<span data-ttu-id="2b502-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b502-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b502-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="2b502-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="2b502-141">Gibt ein Textdokument an.</span><span class="sxs-lookup"><span data-stu-id="2b502-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="2b502-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="2b502-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="2b502-143">Gibt ein Textdokument an.</span><span class="sxs-lookup"><span data-stu-id="2b502-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b502-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b502-144">See Also</span></span>  
 [<span data-ttu-id="2b502-145">Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="2b502-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
