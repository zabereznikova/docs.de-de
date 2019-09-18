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
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053243"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="5f218-102">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="5f218-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="5f218-103">Die .NET Framework wird ständig weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="5f218-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="5f218-104">Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Features out-of-Band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="5f218-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="5f218-105">In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5f218-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="5f218-106">Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen.</span><span class="sxs-lookup"><span data-stu-id="5f218-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="5f218-107">Beispielsweise macht die <xref:System.Text.CodePagesEncodingProvider> -Klasse Code Page Codierungen für UWP-apps verfügbar, die mithilfe des-.NET Framework entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f218-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="5f218-108">Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f218-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="5f218-109">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="5f218-109">OOB projects</span></span>
  
| <span data-ttu-id="5f218-110">Projekt</span><span class="sxs-lookup"><span data-stu-id="5f218-110">Project</span></span> | <span data-ttu-id="5f218-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f218-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="5f218-112">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="5f218-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="5f218-113">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="5f218-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="5f218-114">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="5f218-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="5f218-115">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="5f218-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="5f218-116">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="5f218-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="5f218-117">Projekt</span><span class="sxs-lookup"><span data-stu-id="5f218-117">Project</span></span> | <span data-ttu-id="5f218-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f218-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="5f218-119">Erweitert die <xref:System.Text.EncodingProvider> -Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen.</span><span class="sxs-lookup"><span data-stu-id="5f218-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="5f218-120">Private APIs</span><span class="sxs-lookup"><span data-stu-id="5f218-120">Private APIs</span></span>  

<span data-ttu-id="5f218-121">Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5f218-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
| <span data-ttu-id="5f218-122">Name der API</span><span class="sxs-lookup"><span data-stu-id="5f218-122">API Name</span></span> |
| -------- |
| [<span data-ttu-id="5f218-123">System .net. Connection-Klasse</span><span class="sxs-lookup"><span data-stu-id="5f218-123">System.Net.Connection Class</span></span>](connection.md) |
| [<span data-ttu-id="5f218-124">System .net. Connection. m\_-beschreitelist-Feld</span><span class="sxs-lookup"><span data-stu-id="5f218-124">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md) |
| [<span data-ttu-id="5f218-125">System .net. connectiongroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="5f218-125">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md) |
| [<span data-ttu-id="5f218-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span><span class="sxs-lookup"><span data-stu-id="5f218-126">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md) |
| [<span data-ttu-id="5f218-127">System .net. coreresponabdata-Klasse</span><span class="sxs-lookup"><span data-stu-id="5f218-127">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md) |
| [<span data-ttu-id="5f218-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span><span class="sxs-lookup"><span data-stu-id="5f218-128">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md) |
| [<span data-ttu-id="5f218-129">Feld "System .net. coreresponsedata\_. m" (Statuscode)</span><span class="sxs-lookup"><span data-stu-id="5f218-129">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md) |
| [<span data-ttu-id="5f218-130">System .net. HttpWebRequest. \_Autoreumleitungen-Feld</span><span class="sxs-lookup"><span data-stu-id="5f218-130">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md) |
| [<span data-ttu-id="5f218-131">System .net. HttpWebRequest. \_Coreresponse-Feld</span><span class="sxs-lookup"><span data-stu-id="5f218-131">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md) |
| [<span data-ttu-id="5f218-132">System .net. HttpWebRequest. \_Feld "HttpResponse"</span><span class="sxs-lookup"><span data-stu-id="5f218-132">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md) |
| [<span data-ttu-id="5f218-133">System .net. Service Point. m\_connectiongrouplist-Feld</span><span class="sxs-lookup"><span data-stu-id="5f218-133">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md) |
| [<span data-ttu-id="5f218-134">System .net. ServicePointManager. s\_servicepointtables-Feld</span><span class="sxs-lookup"><span data-stu-id="5f218-134">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md) |
| [<span data-ttu-id="5f218-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span><span class="sxs-lookup"><span data-stu-id="5f218-135">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [<span data-ttu-id="5f218-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span><span class="sxs-lookup"><span data-stu-id="5f218-136">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md) |
| [<span data-ttu-id="5f218-137">System.Windows.Forms.Design.DataMemberListEditor Class</span><span class="sxs-lookup"><span data-stu-id="5f218-137">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a><span data-ttu-id="5f218-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f218-138">See also</span></span>

- [<span data-ttu-id="5f218-139">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="5f218-139">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
