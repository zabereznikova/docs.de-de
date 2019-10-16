---
title: Zusätzliche Klassenbibliotheken und APIs
ms.date: 10/09/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: b869ca2f5e17db9a204a8b757b5e24ebb209d7c5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395660"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="3b4b2-102">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="3b4b2-102">Additional class libraries and APIs</span></span>

<span data-ttu-id="3b4b2-103">Die .NET Framework wird ständig weiterentwickelt.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-103">The .NET Framework is constantly evolving.</span></span> <span data-ttu-id="3b4b2-104">Um die plattformübergreifende Entwicklung zu verbessern und frühzeitig neue Funktionen einzuführen, werden neue Features out-of-Band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-104">To improve cross-platform development and introduce new functionality early, new features are released out of band (OOB).</span></span> <span data-ttu-id="3b4b2-105">In diesem Thema werden die OOB-Projekte aufgeführt, für die eine Dokumentation bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-105">This topic lists the OOB projects that we provide documentation for.</span></span>  
  
<span data-ttu-id="3b4b2-106">Darüber hinaus wurden einige Bibliotheken speziell für bestimmte Plattformen oder Implementierungen von .NET Framework entworfen.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-106">In addition, some libraries target specific platforms or implementations of the .NET Framework.</span></span> <span data-ttu-id="3b4b2-107">Beispielsweise macht die Klasse <xref:System.Text.CodePagesEncodingProvider> Code Page Codierungen für UWP-apps verfügbar, die mithilfe des .NET Framework entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-107">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using the .NET Framework.</span></span> <span data-ttu-id="3b4b2-108">Diese Bibliotheken werden in diesem Thema ebenfalls aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-108">This topic lists these libraries as well.</span></span>  
  
## <a name="oob-projects"></a><span data-ttu-id="3b4b2-109">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="3b4b2-109">OOB projects</span></span>
  
| <span data-ttu-id="3b4b2-110">Projekt</span><span class="sxs-lookup"><span data-stu-id="3b4b2-110">Project</span></span> | <span data-ttu-id="3b4b2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b4b2-111">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="3b4b2-112">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-112">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="3b4b2-113">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-113">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="3b4b2-114">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-114">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>| 
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="3b4b2-115">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-115">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="3b4b2-116">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="3b4b2-116">Platform-specific libraries</span></span>
  
| <span data-ttu-id="3b4b2-117">Projekt</span><span class="sxs-lookup"><span data-stu-id="3b4b2-117">Project</span></span> | <span data-ttu-id="3b4b2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b4b2-118">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="3b4b2-119">Erweitert die <xref:System.Text.EncodingProvider>-Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-119">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="3b4b2-120">Private APIs</span><span class="sxs-lookup"><span data-stu-id="3b4b2-120">Private APIs</span></span>  

<span data-ttu-id="3b4b2-121">Diese APIs unterstützen die Produktinfrastruktur. Sie sind nicht für eine direkte Verwendung im Code vorgesehen und werden dafür auch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3b4b2-121">These APIs support the product infrastructure and are not intended/supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="3b4b2-122">Microsoft. SqlServer. Server. smiorderproperty. Item-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3b4b2-122">Microsoft.SqlServer.Server.SmiOrderProperty.Item Property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="3b4b2-123">System. Exception. prepforremoting-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-123">System.Exception.PrepForRemoting Method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="3b4b2-124">System. Data. SqlTypes. SqlChars. Stream (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="3b4b2-124">System.Data.SqlTypes.SqlChars.Stream Property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="3b4b2-125">System. Data. SqlTypes. SqlStreamChars-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="3b4b2-125">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="3b4b2-126">System. Data. SqlTypes. SqlStreamChars. CanSeek-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3b4b2-126">System.Data.SqlTypes.SqlStreamChars.CanSeek Property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="3b4b2-127">System. Data. SqlTypes. SqlStreamChars. IsNull (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="3b4b2-127">System.Data.SqlTypes.SqlStreamChars.IsNull Property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="3b4b2-128">System. Data. SqlTypes. SqlStreamChars. length (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="3b4b2-128">System.Data.SqlTypes.SqlStreamChars.Length Property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="3b4b2-129">System. Data. SqlTypes. SqlStreamChars. Close-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-129">System.Data.SqlTypes.SqlStreamChars.Close Method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="3b4b2-130">System. Data. SqlTypes. SqlStreamChars. verwerfen-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-130">System.Data.SqlTypes.SqlStreamChars.Dispose Method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="3b4b2-131">System. Data. SqlTypes. SqlStreamChars. Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-131">System.Data.SqlTypes.SqlStreamChars.Flush Method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="3b4b2-132">System. Data. SqlTypes. SqlStreamChars. Read-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-132">System.Data.SqlTypes.SqlStreamChars.Read Method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="3b4b2-133">System. Data. SqlTypes. SqlStreamChars. Seek-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-133">System.Data.SqlTypes.SqlStreamChars.Seek Method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="3b4b2-134">System. Data. SqlTypes. SqlStreamChars. SetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-134">System.Data.SqlTypes.SqlStreamChars.SetLength Method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="3b4b2-135">System. Data. SqlTypes. SqlStreamChars. Write-Methode</span><span class="sxs-lookup"><span data-stu-id="3b4b2-135">System.Data.SqlTypes.SqlStreamChars.Write Method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="3b4b2-136">System .net. Connection-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b4b2-136">System.Net.Connection Class</span></span>](connection.md)
* [<span data-ttu-id="3b4b2-137">System .net. Connection. m @ no__t-1schreitelist-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-137">System.Net.Connection.m\_WriteList Field</span></span>](m_writelist.md)
* [<span data-ttu-id="3b4b2-138">System .net. connectiongroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b4b2-138">System.Net.ConnectionGroup Class</span></span>](connectiongroup.md)
* [<span data-ttu-id="3b4b2-139">System .net. connectiongroup. m @ no__t-1connectionlist-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-139">System.Net.ConnectionGroup.m\_ConnectionList Field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="3b4b2-140">System .net. coreresponabdata-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b4b2-140">System.Net.CoreResponseData Class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="3b4b2-141">System .net. coreresponabdata. m @ no__t-1response Headers-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-141">System.Net.CoreResponseData.m\_ResponseHeaders Field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="3b4b2-142">System .net. coreresponsedata. m @ no__t-1Status Code-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-142">System.Net.CoreResponseData.m\_StatusCode Field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="3b4b2-143">System .net. HttpWebRequest. \_autoreumleitungen-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-143">System.Net.HttpWebRequest.\_AutoRedirects Field</span></span>](_autoredirects.md)
* [<span data-ttu-id="3b4b2-144">System .net. HttpWebRequest. \_coreresponse-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-144">System.Net.HttpWebRequest.\_CoreResponse Field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="3b4b2-145">System .net. HttpWebRequest. \_httpresponse-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-145">System.Net.HttpWebRequest.\_HttpResponse Field</span></span>](_httpresponse.md)
* [<span data-ttu-id="3b4b2-146">System .net. Service Point. m @ no__t-1connectiongrouplist-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-146">System.Net.ServicePoint.m\_ConnectionGroupList Field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="3b4b2-147">System .net. ServicePointManager. s @ no__t-1servicepoint\feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-147">System.Net.ServicePointManager.s\_ServicePointTable Field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="3b4b2-148">System. Windows. Diagnostics. visualdiagnostics. s @ no__t-1isdebuggercheckdisabledfortesttargets-Feld</span><span class="sxs-lookup"><span data-stu-id="3b4b2-148">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="3b4b2-149">System. Windows. Forms. Design. DataMemberFieldEditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b4b2-149">System.Windows.Forms.Design.DataMemberFieldEditor Class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="3b4b2-150">System. Windows. Forms. Design. datamemberlisteditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="3b4b2-150">System.Windows.Forms.Design.DataMemberListEditor Class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="3b4b2-151">ADODB. Verbindungsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b4b2-151">adodb.Connection Interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="3b4b2-152">ADODB. Eventreason-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="3b4b2-152">adodb.EventReason Enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="3b4b2-153">ADODB. EventStatus-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="3b4b2-153">adodb.EventStatus Enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="3b4b2-154">stdole. Dispparameams-Struktur</span><span class="sxs-lookup"><span data-stu-id="3b4b2-154">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="3b4b2-155">stdole. EXCEPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="3b4b2-155">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="3b4b2-156">stdole. IFont.Name-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3b4b2-156">stdole.IFont.Name Property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="3b4b2-157">stdole. IFontDisp-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b4b2-157">stdole.IFontDisp Interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="3b4b2-158">stdole. IPicture. Handle-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3b4b2-158">stdole.IPicture.Handle Property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="3b4b2-159">stdole. IPictureDisp. handle (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="3b4b2-159">stdole.IPictureDisp.Handle Property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="3b4b2-160">stdole. StdFont-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b4b2-160">stdole.StdFont Interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="3b4b2-161">stdole. StdPicture-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b4b2-161">stdole.StdPicture Interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="3b4b2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b4b2-162">See also</span></span>

* [<span data-ttu-id="3b4b2-163">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="3b4b2-163">The .NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
