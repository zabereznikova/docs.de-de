---
title: Technologiebeispiel für die Genericsserialisierung in Webdiensten
ms.date: 03/30/2017
ms.assetid: cdc15ea4-f678-4729-8ebe-188ae720bef7
ms.openlocfilehash: 467bfe1fd9eb8a0222385c34cb29a90df00dc937
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960747"
---
# <a name="web-services-generics-serialization-technology-sample"></a><span data-ttu-id="1de9e-102">Technologiebeispiel für die Genericsserialisierung in Webdiensten</span><span class="sxs-lookup"><span data-stu-id="1de9e-102">Web Services Generics Serialization Technology Sample</span></span>
[<span data-ttu-id="1de9e-103">Beispiel herunterladen</span><span class="sxs-lookup"><span data-stu-id="1de9e-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/GenericsSerialization.zip.exe)  
  
 <span data-ttu-id="1de9e-104">In diesem Beispiel wird die Verwendung und Steuerung der Genericsserialisierung in ASP.NET-Webdiensten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1de9e-104">This sample shows how to use and control the serialization of generics in ASP.NET Web Services.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="1de9e-105">So erstellen Sie das Beispiel mithilfe von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1de9e-105">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="1de9e-106">Öffnen Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neue Website** aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-106">Open Visual Studio and select **New Web Site** from the **File** menu.</span></span>  
  
2. <span data-ttu-id="1de9e-107">Wählen Sie im Dialogfeld **Neue Website** im linken Bereich die gewünschte Programmiersprache und im rechten Bereich **ASP.NET Web Service** aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-107">In the **New Web Site** dialog, select from the left pane your desired programming language, then from the right pane, select **ASP.NET Web Service**.</span></span>  
  
3. <span data-ttu-id="1de9e-108">Klicken Sie auf **Durchsuchen**, und navigieren Sie zum Unterverzeichnis „\CS\GenericsService“.</span><span class="sxs-lookup"><span data-stu-id="1de9e-108">Click **Browse** and navigate to the \CS\GenericsService subdirectory.</span></span>  
  
4. <span data-ttu-id="1de9e-109">Wählen Sie "Service.asmx" aus, um die Datei in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-109">Select Service.asmx to open the file in Visual Studio.</span></span>  
  
5. <span data-ttu-id="1de9e-110">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1de9e-110">On the **Build** menu, click **Build Solution**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1de9e-111">Die ersten fünf Schritte in dieser Liste sind optional.</span><span class="sxs-lookup"><span data-stu-id="1de9e-111">The first five steps in this list are optional.</span></span> <span data-ttu-id="1de9e-112">Die .NET Framework-Laufzeit generiert bei der ersten Anforderung des Diensts automatisch den Webdienst.</span><span class="sxs-lookup"><span data-stu-id="1de9e-112">The .NET Framework runtime will automatically generate the Web service the first time the service is requested.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1de9e-113">Die folgenden Schritte sind erforderlich, um das Beispiel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-113">The following steps are required to build the sample.</span></span>  
  
1. <span data-ttu-id="1de9e-114">Öffnen Sie den Datei-Explorer, und navigieren Sie zum Unterverzeichnis „\CS“.</span><span class="sxs-lookup"><span data-stu-id="1de9e-114">Open File Explorer and navigate to the \CS subdirectory.</span></span>  
  
2. <span data-ttu-id="1de9e-115">Klicken Sie mit der rechten Maustaste auf das Symbol für das Verzeichnis „GenericsService“, und wählen Sie **Freigabe und Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-115">Right-click the icon for the GenericsService subdirectory, and select **Sharing and Security**.</span></span>  
  
3. <span data-ttu-id="1de9e-116">Wählen Sie auf der Registerkarte **Webfreigabe** die Option **Diesen Ordner freigeben** aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-116">In the **Web Sharing** tab, select **Share this Folder**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1de9e-117">Merken Sie sich den Namen des virtuellen Verzeichnisses, das im Bereich **Aliase** aufgeführt wird. Sie brauchen ihn zum Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="1de9e-117">Take note of the virtual directory name that is listed in the **Aliases** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-build-the-sample-using-internet-information-services"></a><span data-ttu-id="1de9e-118">So erstellen Sie das Beispiel mit Internetinformationsdienste</span><span class="sxs-lookup"><span data-stu-id="1de9e-118">To build the sample using Internet Information Services</span></span>  
  
1. <span data-ttu-id="1de9e-119">Öffnen Sie das Verwaltungs-Snap-In von **Internetinformationsdienste**, und erweitern Sie **Websites**.</span><span class="sxs-lookup"><span data-stu-id="1de9e-119">Open the **Internet Information Services** management snap-in and expand **Web Sites**.</span></span>  
  
2. <span data-ttu-id="1de9e-120">Klicken Sie mit der linken Maustaste auf **Standardwebsite**, und wählen Sie **Neu** und dann **Virtuelles Verzeichnis**, um den **Assistenten zum Erstellen eines virtuellen Verzeichnisses** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-120">Left-click **Default Web Site**, select **New**, and then select **Virtual Directory?** to create the **Virtual Directory Creation Wizard**.</span></span>  
  
3. <span data-ttu-id="1de9e-121">Klicken Sie auf **Weiter**, geben Sie den öffentlichen Alias für das virtuelle Verzeichnis ein, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1de9e-121">Click **Next**, enter the public alias for your virtual directory, and click **Next**.</span></span>  
  
4. <span data-ttu-id="1de9e-122">Geben Sie den Pfad zum Verzeichnis ein, in dem Sie das Beispiel gespeichert haben (normalerweise das Unterverzeichnis „\CS\GenericsService“), und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="1de9e-122">Enter the path to the directory where you saved the sample (normally the \CS\GenericsService subdirectory) and click **Next**.</span></span> <span data-ttu-id="1de9e-123">Klicken Sie auf **Weiter**, um den Assistenten zu beenden.</span><span class="sxs-lookup"><span data-stu-id="1de9e-123">Click **Next** to finish the wizard.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1de9e-124">Merken Sie sich den Namen des virtuellen Verzeichnisses, das im Bereich **Alias** aufgeführt wird. Sie brauchen ihn zum Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="1de9e-124">Take note of the virtual directory name that is listed in the **Alias** pane, because you will need it to run the sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="1de9e-125">So führen Sie das Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="1de9e-125">To run the sample</span></span>  
  
1. <span data-ttu-id="1de9e-126">Öffnen Sie ein Browserfenster, und wählen Sie die Adressleiste aus.</span><span class="sxs-lookup"><span data-stu-id="1de9e-126">Open a browser window and select its address bar.</span></span>  
  
2. <span data-ttu-id="1de9e-127">Geben Sie `http://localhost/[virtual directory]/Service.asmx` ein, wobei `[virtual directory]` das virtuelle Verzeichnis darstellt, das Sie beim Erstellen des Beispiels angelegt haben.</span><span class="sxs-lookup"><span data-stu-id="1de9e-127">Type `http://localhost/[virtual directory]/Service.asmx`, where `[virtual directory]` represents the virtual directory you created when you built the sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1de9e-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1de9e-128">Remarks</span></span>  
 <span data-ttu-id="1de9e-129">Im Beispiel wird eine Standard-ASP.NET-Seite angezeigt, die Links zur Definition des Webdiensts enthält.</span><span class="sxs-lookup"><span data-stu-id="1de9e-129">The sample displays a default ASP.NET page that contains links to the definition of the Web Service.</span></span> <span data-ttu-id="1de9e-130">Sie können den Quellcode für den Webdienst ändern und zusätzlich die Anzeige anpassen.</span><span class="sxs-lookup"><span data-stu-id="1de9e-130">You can customize the display in addition to modifying the source code for the Web service.</span></span> <span data-ttu-id="1de9e-131">Weitere Informationen finden Sie unter [Erstellen von XML-Webdienstclients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1de9e-131">For more information, see [Building XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w3h45ebk(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1de9e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1de9e-132">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Web.Services>
- <xref:System.Xml.Serialization>
- [<span data-ttu-id="1de9e-133">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1de9e-133">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- <span data-ttu-id="1de9e-134">[Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1de9e-134">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
