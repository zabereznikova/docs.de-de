---
title: ByteStream-Encoder
ms.date: 03/30/2017
ms.assetid: e674a8ab-f79a-4a93-b984-54b34392dafc
ms.openlocfilehash: ab9ccf47527dcf7f01f272f09b3b341d30fbd8d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499679"
---
# <a name="bytestream-encoder"></a><span data-ttu-id="5412c-102">ByteStream-Encoder</span><span class="sxs-lookup"><span data-stu-id="5412c-102">ByteStream Encoder</span></span>
<span data-ttu-id="5412c-103">In diesem Beispiel wird veranschaulicht, wie eine `ByteStreamHttpBinding` erstellt wird, eine <xref:System.ServiceModel.Channels.Binding>, die die Funktionalität des Bytestreamencoder veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5412c-103">This sample demonstrates how to create a `ByteStreamHttpBinding`, a <xref:System.ServiceModel.Channels.Binding> that demonstrates the functionality of the byte stream encoder.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5412c-104">Diskussion</span><span class="sxs-lookup"><span data-stu-id="5412c-104">Discussion</span></span>  
 <span data-ttu-id="5412c-105">In diesem Beispiel wird veranschaulicht, wie eine Standard-<xref:System.ServiceModel.Channels.Binding> mithilfe der Standardbindungselemente <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.HttpTransportBindingElement> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5412c-105">This sample demonstrates how to create a standard <xref:System.ServiceModel.Channels.Binding> using the standard binding elements <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span> <span data-ttu-id="5412c-106">In diesem Beispiel wird gezeigt, wie mit dem Bytestreamencoder ein Bild hochgeladen und heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="5412c-106">This sample shows how to use the byte stream encoder to upload and download an image.</span></span> <span data-ttu-id="5412c-107">Die Bytedatenstromencoder-Funktion unterstützt nur den HTTP-Transport und bietet keine Unterstützung von Funktionen wie zuverlässiges Messaging oder Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="5412c-107">The byte stream encoder feature only supports the HTTP transport and it does not support features such as reliable messaging or security.</span></span> <span data-ttu-id="5412c-108">Die einzige unterstützte <xref:System.ServiceModel.Channels.MessageVersion> ist <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="5412c-108">The only <xref:System.ServiceModel.Channels.MessageVersion> supported is <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5412c-109">Wenn Sie dieses Beispiel mit [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] oder unter [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)] ausführen, stellen Sie sicher, dass Sie [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="5412c-109">If you are running this sample in [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] or [!INCLUDE[win7_client_firstref](../../../../includes/win7-client-firstref-md.md)], ensure that you are running [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] with elevated privileges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5412c-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5412c-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5412c-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5412c-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5412c-112">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="5412c-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5412c-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5412c-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\ByteStreamEncoder`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5412c-114">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="5412c-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5412c-115">Öffnen Sie die Datei ByteStreamHttpBinding.sln in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5412c-115">Open the ByteStreamHttpBinding.sln file in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="5412c-116">Starten Sie eine neue Instanz des ByteStreamHttpBindingServer-Projekts, indem Sie das Projekt im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Debuggen**, und klicken Sie dann **neue Instanz starten** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="5412c-116">Start a new instance of the ByteStreamHttpBindingServer project by right-clicking the project in the Solution Explorer and selecting **Debug**, and then **Start new instance** from the context menu.</span></span>  
  
3.  <span data-ttu-id="5412c-117">Starten Sie eine neue Instanz des ByteStreamHttpBindingClient-Projekts, indem Sie das Projekt im Projektmappen-Explorer mit der rechten Maustaste und auswählen **Debuggen**, **neue Instanz starten** aus dem Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="5412c-117">Start a new instance of the ByteStreamHttpBindingClient project by right-clicking the project in the Solution Explorer and selecting **Debug**, **Start new instance** from the context menu.</span></span>
