---
title: "Zusätzliche Klassenbibliotheken und APIs | Microsoft-Dokumentation"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: 12
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: b53b8acc2a6c56db6a9d8a9b7c685a2d400a53e1
ms.openlocfilehash: 34815268b707aa70d174a1bbc04c32276db8412d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---

# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="f70bb-102">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="f70bb-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="f70bb-103">Um die plattformübergreifende Entwicklung für das sich ständig weiterentwickelnde .NET Framework für unsere Kunden rechtzeitig zu verbessern oder neue Funktionalität einzuführen, werden neue Funktionen out-of-band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="f70bb-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="f70bb-104">In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f70bb-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="f70bb-105">Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen.</span><span class="sxs-lookup"><span data-stu-id="f70bb-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="f70bb-106">Die <xref:System.Text.CodePagesEncodingProvider>-Klasse beispielsweise macht Codepagecodierungen für UWP-Apps verfügbar, die mit .NET Framework entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="f70bb-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="f70bb-107">Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f70bb-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="f70bb-108">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="f70bb-108">OOB projects</span></span>
  
| <span data-ttu-id="f70bb-109">Projekt</span><span class="sxs-lookup"><span data-stu-id="f70bb-109">Project</span></span> | <span data-ttu-id="f70bb-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f70bb-110">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="f70bb-111"><xref:System.Collections.Immutable></span><span class="sxs-lookup"><span data-stu-id="f70bb-111"><xref:System.Collections.Immutable></span></span> | <span data-ttu-id="f70bb-112">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="f70bb-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <span data-ttu-id="f70bb-113"><xref:System.Net.Http.WinHttpHandler></span><span class="sxs-lookup"><span data-stu-id="f70bb-113"><xref:System.Net.Http.WinHttpHandler></span></span> | <span data-ttu-id="f70bb-114">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> basierend auf der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="f70bb-114">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="f70bb-115">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="f70bb-115">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="f70bb-116">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="f70bb-116">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <span data-ttu-id="f70bb-117"><xref:System.Threading.Tasks.Dataflow></span><span class="sxs-lookup"><span data-stu-id="f70bb-117"><xref:System.Threading.Tasks.Dataflow></span></span> | <span data-ttu-id="f70bb-118">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f70bb-118">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="f70bb-119">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="f70bb-119">Platform-specific libraries</span></span>
  
| <span data-ttu-id="f70bb-120">Projekt</span><span class="sxs-lookup"><span data-stu-id="f70bb-120">Project</span></span> | <span data-ttu-id="f70bb-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f70bb-121">Description</span></span> |  
| ------- | ----------- |  
| <span data-ttu-id="f70bb-122"><xref:System.Text.CodePagesEncodingProvider></span><span class="sxs-lookup"><span data-stu-id="f70bb-122"><xref:System.Text.CodePagesEncodingProvider></span></span> | <span data-ttu-id="f70bb-123">Erweitert die <xref:System.Text.EncodingProvider>-Klasse, um Codepagecodierungen für Apps verfügbar zu machen, die für die universelle Windows-Plattform entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="f70bb-123">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="f70bb-124">Private APIs</span><span class="sxs-lookup"><span data-stu-id="f70bb-124">Private APIs</span></span>  

<span data-ttu-id="f70bb-125">Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f70bb-125">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="f70bb-126">Name der API</span><span class="sxs-lookup"><span data-stu-id="f70bb-126">API Name</span></span> |  
| -------- |  
| [<span data-ttu-id="f70bb-127">s_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="f70bb-127">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |  
| [<span data-ttu-id="f70bb-128">DataMemberFieldEditor Class</span><span class="sxs-lookup"><span data-stu-id="f70bb-128">DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |  
| [<span data-ttu-id="f70bb-129">DataMemberListEditor Class</span><span class="sxs-lookup"><span data-stu-id="f70bb-129">DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |  
  
## <a name="see-also"></a><span data-ttu-id="f70bb-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f70bb-130">See also</span></span>

[<span data-ttu-id="f70bb-131">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="f70bb-131">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)

