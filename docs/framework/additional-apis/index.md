---
title: "Zusätzliche Klassenbibliotheken und APIs"
ms.custom: 
ms.date: 04/12/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c22de3ed401e0be10b155649395da43cedb35e6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="15918-102">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="15918-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="15918-103">Um die plattformübergreifende Entwicklung für das sich ständig weiterentwickelnde .NET Framework für unsere Kunden rechtzeitig zu verbessern oder neue Funktionalität einzuführen, werden neue Funktionen out-of-band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="15918-103">The .NET Framework is constantly evolving and in order to improve cross-platform development or to introduce new functionality early to our customers, we release new features out of band (OOB).</span></span> <span data-ttu-id="15918-104">In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="15918-104">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="15918-105">Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen.</span><span class="sxs-lookup"><span data-stu-id="15918-105">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="15918-106">Z. B. die <xref:System.Text.CodePagesEncodingProvider> Klasse stellt codepagecodierungen uwp-apps mit .NET Framework entwickelt wurden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="15918-106">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="15918-107">Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="15918-107">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="15918-108">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="15918-108">OOB projects</span></span>
  
| <span data-ttu-id="15918-109">Projekt</span><span class="sxs-lookup"><span data-stu-id="15918-109">Project</span></span> | <span data-ttu-id="15918-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15918-110">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="15918-111">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="15918-111">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="15918-112">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="15918-112">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="15918-113">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="15918-113">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="15918-114">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="15918-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="15918-115">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="15918-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="15918-116">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="15918-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="15918-117">Projekt</span><span class="sxs-lookup"><span data-stu-id="15918-117">Project</span></span> | <span data-ttu-id="15918-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15918-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="15918-119">Erweitert die <xref:System.Text.EncodingProvider> Klasse, um die codepagecodierungen für apps verfügbar zu machen, die auf Uwp abzielen.</span><span class="sxs-lookup"><span data-stu-id="15918-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="15918-120">Private APIs</span><span class="sxs-lookup"><span data-stu-id="15918-120">Private APIs</span></span>  

<span data-ttu-id="15918-121">Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15918-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="15918-122">Name der API</span><span class="sxs-lookup"><span data-stu-id="15918-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="15918-123">System.Net.Connection-Klasse</span><span class="sxs-lookup"><span data-stu-id="15918-123">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="15918-124">System.Net.Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-124">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="15918-125">System.Net.ConnectionGroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="15918-125">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="15918-126">System.Net.ConnectionGroup.m\_ConnectionList-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="15918-127">System.NET.HttpWebRequest". \_HttpResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-127">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="15918-128">System.NET.HttpWebRequest". \_AutoRedirects-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-128">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="15918-129">System.Net.ServicePoint.m\_ConnectionGroupList-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-129">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="15918-130">System.Net.ServicePointManager.s\_ServicePointTable-Feld</span><span class="sxs-lookup"><span data-stu-id="15918-130">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="15918-131">System.Windows.Diagnostics.VisualDiagnostics.s\_IsDebuggerCheckDisabledForTestPurposes Feld</span><span class="sxs-lookup"><span data-stu-id="15918-131">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="15918-132">System.Windows.Forms.Design.DataMemberFieldEditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="15918-132">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="15918-133">System.Windows.Forms.Design.DataMemberListEditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="15918-133">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="15918-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15918-134">See also</span></span>

[<span data-ttu-id="15918-135">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="15918-135">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
