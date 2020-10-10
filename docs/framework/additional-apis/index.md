---
title: Zusätzliche Klassenbibliotheken und APIs
description: Erkunden Sie zusätzliche Klassenbibliotheken und APIs in .net, einschließlich out-of-Band-Projekte (OOB), plattformspezifischen Bibliotheken und privaten APIs.
ms.date: 08/11/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 55cb37cc2c9184eeb55ee0aab39e97f4a3f7b7d8
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877638"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="c0ee5-103">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="c0ee5-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="c0ee5-104">In diesem Artikel werden .NET Framework APIs aufgelistet, die entweder out-of-Band veröffentlicht wurden, eine bestimmte Plattform als Zielplattform oder private oder interne Typen sind.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="c0ee5-105">OOB-Projekte</span><span class="sxs-lookup"><span data-stu-id="c0ee5-105">OOB projects</span></span>

<span data-ttu-id="c0ee5-106">Um die plattformübergreifende Entwicklung zu verbessern und neue Funktionen frühzeitig einzuführen, wurden einige .NET Framework Features out-of-Band (OOB) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="c0ee5-107">Projekt</span><span class="sxs-lookup"><span data-stu-id="c0ee5-107">Project</span></span> | <span data-ttu-id="c0ee5-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0ee5-108">Description</span></span> |
| ------- | ----------- |
| <xref:System.Collections.Immutable> | <span data-ttu-id="c0ee5-109">Bietet Auflistungen, die threadsicher sind und garantiert nie ihren Inhalt ändern.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="c0ee5-110">Stellt einen Meldungshandler für <xref:System.Net.Http.HttpClient> auf Grundlage der WinHTTP-Schnittstelle von Windows bereit.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="c0ee5-111">Stellt eine Bibliothek von Vektortypen bereit, die die SIMD-Hardwarebeschleunigung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="c0ee5-112">Die TPL-Datenflussbibliothek (Task Parallel Library) stellt Datenflusskomponenten bereit, um die Stabilität von nebenläufigkeitsfähigen Anwendungen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |

## <a name="platform-specific-libraries"></a><span data-ttu-id="c0ee5-113">Plattformspezifische Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="c0ee5-113">Platform-specific libraries</span></span>

<span data-ttu-id="c0ee5-114">Einige Bibliotheken richten sich an bestimmte Plattformen.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="c0ee5-115">Beispielsweise macht die- <xref:System.Text.CodePagesEncodingProvider> Klasse Code Page Codierungen für UWP-apps verfügbar, die mit .NET Framework entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>

| <span data-ttu-id="c0ee5-116">Projekt</span><span class="sxs-lookup"><span data-stu-id="c0ee5-116">Project</span></span> | <span data-ttu-id="c0ee5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0ee5-117">Description</span></span> |
| ------- | ----------- |
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="c0ee5-118">Erweitert die- <xref:System.Text.EncodingProvider> Klasse, um Code Page Codierungen für Apps zur Verfügung zu stellen, die auf die universelle Windows-Plattform abzielen.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |

## <a name="private-apis"></a><span data-ttu-id="c0ee5-119">Private APIs</span><span class="sxs-lookup"><span data-stu-id="c0ee5-119">Private APIs</span></span>

<span data-ttu-id="c0ee5-120">Diese APIs unterstützen die Produkt Infrastruktur und sind nicht für die direkte Verwendung im Code vorgesehen oder werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c0ee5-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>

* [<span data-ttu-id="c0ee5-121">Microsoft. SqlServer. Server. smiorderproperty. Item-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0ee5-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="c0ee5-122">System. Exception. prepforremoting-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="c0ee5-123">System. Data. SqlTypes. SqlChars. Stream (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="c0ee5-124">System. Data. SqlTypes. SqlStreamChars-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="c0ee5-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="c0ee5-125">System. Data. SqlTypes. SqlStreamChars. CanSeek-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0ee5-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="c0ee5-126">System. Data. SqlTypes. SqlStreamChars. IsNull (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="c0ee5-127">System. Data. SqlTypes. SqlStreamChars. length (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="c0ee5-128">System. Data. SqlTypes. SqlStreamChars. Close-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="c0ee5-129">System. Data. SqlTypes. SqlStreamChars. verwerfen-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="c0ee5-130">System. Data. SqlTypes. SqlStreamChars. Flush-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="c0ee5-131">System. Data. SqlTypes. SqlStreamChars. Read-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="c0ee5-132">System. Data. SqlTypes. SqlStreamChars. Seek-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="c0ee5-133">System. Data. SqlTypes. SqlStreamChars. SetLength-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="c0ee5-134">System. Data. SqlTypes. SqlStreamChars. Write-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="c0ee5-135">System. IO. MemoryStream. internalgetoriginandlength-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="c0ee5-136">System .net. comnettos-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="c0ee5-137">System .net. Connection-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="c0ee5-138">System .net. Connection. m- \_ beschreitelist-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="c0ee5-139">System .net. connectiongroup-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="c0ee5-140">Feld "System .net. connectiongroup. m \_ connectionlist"</span><span class="sxs-lookup"><span data-stu-id="c0ee5-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="c0ee5-141">System .net. connectstream. Connection-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0ee5-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="c0ee5-142">System .net. coreresponabdata-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="c0ee5-143">Feld "System .net. coreresponabdata. m \_ Response Headers"</span><span class="sxs-lookup"><span data-stu-id="c0ee5-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="c0ee5-144">Feld "System .net. coreresponsedata. m" ( \_ Statuscode)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="c0ee5-145">System .net. exceptionhelper-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="c0ee5-146">System .net. httpStatus Description-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="c0ee5-147">System .net. HttpWebRequest. \_ Autoreumleitungen-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="c0ee5-148">System .net. HttpWebRequest. \_ Coreresponse-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="c0ee5-149">System .net. HttpWebRequest. \_ Feld "HttpResponse"</span><span class="sxs-lookup"><span data-stu-id="c0ee5-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="c0ee5-150">System .net. Logging-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="c0ee5-151">System .net. Mail. mailadressssparser-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="c0ee5-152">System .net. Mail. quotedpaar Reader-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="c0ee5-153">System .net. MIME. mailbnfhelper-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="c0ee5-154">System .net. pooledstream. NetworkStream (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="c0ee5-155">System .net. rtcstate-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="c0ee5-156">System .net. Security. sslstate. SslProtocol (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="c0ee5-157">System .net. Service Point. m \_ connectiongrouplist-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="c0ee5-158">System .net. ServicePointManager. closeconnectiongroups-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="c0ee5-159">System .net. ServicePointManager. s \_ servicepointtables-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="c0ee5-160">System.net.TlsStream.m_Worker Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="c0ee5-161">System .net. unsafenclnativemethods-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="c0ee5-162">System .net. WebHeaderCollection. addinternal-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="c0ee5-163">System. Service Model. Channels. Message. bodydestring-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="c0ee5-164">System. Service Model. Channels. Message. Write-starteaders-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="c0ee5-165">System. Web. Compilation. controlbuilderinterceptor-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-165">System.Web.Compilation.ControlBuilderInterceptor class</span></span>](controlbuilderinterceptor-class.md)
* [<span data-ttu-id="c0ee5-166">System. Windows. Controls. GridViewHeaderRowPresenter. findheaderbycolumn-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-166">System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn method</span></span>](system.windows.controls.gridviewheaderrowpresenter.findheaderbycolumn.md)
* [<span data-ttu-id="c0ee5-167">System. Windows. Controls. GridViewHeaderRowPresenter. makeparameentitemscontrolgotfocus-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-167">System.Windows.Controls.GridViewHeaderRowPresenter.MakeParentItemsControlGotFocus method</span></span>](system.windows.controls.gridviewheaderrowpresenter.makeparentitemscontrolgotfocus.md)
* [<span data-ttu-id="c0ee5-168">System. Windows. Controls. GridViewHeaderRowPresenter. prepareheaderdrag-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-168">System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag method</span></span>](system.windows.controls.gridviewheaderrowpresenter.prepareheaderdrag.md)
* [<span data-ttu-id="c0ee5-169">System. Windows. Diagnostics. visualdiagnostics. s \_ isdebuggercheckdisabledfortesttargets-Feld</span><span class="sxs-lookup"><span data-stu-id="c0ee5-169">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="c0ee5-170">System. Windows. Forms. Design. DataMemberFieldEditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-170">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="c0ee5-171">System. Windows. Forms. Design. datamemberlisteditor-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ee5-171">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="c0ee5-172">System.Xml.XmlReader. kreatesqlreader-Methode</span><span class="sxs-lookup"><span data-stu-id="c0ee5-172">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="c0ee5-173">ADODB. Verbindungsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ee5-173">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="c0ee5-174">ADODB. Eventreason-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="c0ee5-174">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="c0ee5-175">ADODB. EventStatus-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="c0ee5-175">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="c0ee5-176">stdole. Dispparameams-Struktur</span><span class="sxs-lookup"><span data-stu-id="c0ee5-176">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="c0ee5-177">stdole. EXCEPINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="c0ee5-177">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="c0ee5-178">stdole. IFont.Name-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0ee5-178">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="c0ee5-179">stdole. IFontDisp-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ee5-179">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="c0ee5-180">stdole. IPicture. Handle-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c0ee5-180">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="c0ee5-181">stdole. IPictureDisp. handle (Eigenschaft)</span><span class="sxs-lookup"><span data-stu-id="c0ee5-181">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="c0ee5-182">stdole. StdFont-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ee5-182">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="c0ee5-183">stdole. StdPicture-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0ee5-183">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)

## <a name="see-also"></a><span data-ttu-id="c0ee5-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0ee5-184">See also</span></span>

* [<span data-ttu-id="c0ee5-185">.NET Framework und Out-of-Band-Releases</span><span class="sxs-lookup"><span data-stu-id="c0ee5-185">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
