---
title: Zusätzliche Klassenbibliotheken und APIs
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 7659dde4a2cb08fc3257d2f613ce4146522072b6
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46528709"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="8bba8-102">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="8bba8-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="8bba8-103">.NET Framework wird ständig weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="8bba8-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="8bba8-104">Um plattformübergreifende Entwicklung zu verbessern und eine neue Funktionalität einem frühen Zeitpunkt einführen, werden neue Features of-Band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="8bba8-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="8bba8-105">In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8bba8-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="8bba8-106">Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen.</span><span class="sxs-lookup"><span data-stu-id="8bba8-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="8bba8-107">Z. B. die <xref:System.Text.CodePagesEncodingProvider> -Klasse stellt codepagecodierungen für UWP-apps mit .NET Framework entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8bba8-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="8bba8-108">Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bba8-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="8bba8-109">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="8bba8-109">OOB projects</span></span>
  
| <span data-ttu-id="8bba8-110">Projekt</span><span class="sxs-lookup"><span data-stu-id="8bba8-110">Project</span></span> | <span data-ttu-id="8bba8-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bba8-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="8bba8-112">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="8bba8-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="8bba8-113">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="8bba8-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| [<span data-ttu-id="8bba8-114">System.Numerics.Vectors</span><span class="sxs-lookup"><span data-stu-id="8bba8-114">System.Numerics.Vectors</span></span>](https://msdn.microsoft.com/library/mt452176.aspx) | <span data-ttu-id="8bba8-115">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="8bba8-115">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="8bba8-116">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="8bba8-116">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="8bba8-117">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="8bba8-117">Platform-specific libraries</span></span>
  
| <span data-ttu-id="8bba8-118">Projekt</span><span class="sxs-lookup"><span data-stu-id="8bba8-118">Project</span></span> | <span data-ttu-id="8bba8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bba8-119">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="8bba8-120">Erweitert die <xref:System.Text.EncodingProvider> Klasse, um codepagecodierungen für apps zur Verfügung stellen, die auf die universelle Windows-Plattform abzielen.</span><span class="sxs-lookup"><span data-stu-id="8bba8-120">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="8bba8-121">Private APIs</span><span class="sxs-lookup"><span data-stu-id="8bba8-121">Private APIs</span></span>  

<span data-ttu-id="8bba8-122">Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8bba8-122">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="8bba8-123">Name der API</span><span class="sxs-lookup"><span data-stu-id="8bba8-123">API Name</span></span> |
| -------- |
| [<span data-ttu-id="8bba8-124">System.Net.Connection-Klasse</span><span class="sxs-lookup"><span data-stu-id="8bba8-124">System.Net.Connection Class</span></span>](../../../docs/framework/additional-apis/connection.md) |
| [<span data-ttu-id="8bba8-125">System.Net.Connection.m\_WriteList-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-125">System.Net.Connection.m\_WriteList Field</span></span>](../../../docs/framework/additional-apis/m_writelist.md) |
| [<span data-ttu-id="8bba8-126">System.Net.ConnectionGroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="8bba8-126">System.Net.ConnectionGroup Class</span></span>](../../../docs/framework/additional-apis/connectiongroup.md) |
| [<span data-ttu-id="8bba8-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="8bba8-127">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [<span data-ttu-id="8bba8-128">System.Net.CoreResponseData-Klasse</span><span class="sxs-lookup"><span data-stu-id="8bba8-128">System.Net.CoreResponseData Class</span></span>](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [<span data-ttu-id="8bba8-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="8bba8-129">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="8bba8-130">System.Net.CoreResponseData.m\_StatusCode-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-130">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="8bba8-131">System.Net.HttpWebRequest. \_AutoRedirects-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-131">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](../../../docs/framework/additional-apis/_autoredirects.md) |
| [<span data-ttu-id="8bba8-132">System.Net.HttpWebRequest. \_CoreResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-132">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="8bba8-133">System.Net.HttpWebRequest. \_HttpResponse-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-133">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](../../../docs/framework/additional-apis/_httpresponse.md) |
| [<span data-ttu-id="8bba8-134">System.Net.ServicePoint.m\_ConnectionGroupList-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-134">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [<span data-ttu-id="8bba8-135">System.Net.ServicePointManager.s\_ServicePointTable-Feld</span><span class="sxs-lookup"><span data-stu-id="8bba8-135">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [<span data-ttu-id="8bba8-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="8bba8-136">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="8bba8-137">System.Windows.Forms.Design.DataMemberFieldEditor Class</span><span class="sxs-lookup"><span data-stu-id="8bba8-137">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [<span data-ttu-id="8bba8-138">System.Windows.Forms.Design.DataMemberListEditor Class</span><span class="sxs-lookup"><span data-stu-id="8bba8-138">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="8bba8-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bba8-139">See also</span></span>

[<span data-ttu-id="8bba8-140">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="8bba8-140">The .NET Framework and Out-of-Band Releases</span></span>](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
