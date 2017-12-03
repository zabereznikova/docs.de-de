---
title: "Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d035e703b79eb184bf06e3e75255e2f987c170
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="d7771-102">Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)</span><span class="sxs-lookup"><span data-stu-id="d7771-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="d7771-103">Zum Ausführen der Beispiele, die über eine sichere Kommunikation mit Internetinformationsdiensten (IIS) verbunden sind, müssen Sie ein Serverzertifikat erstellen und installieren.</span><span class="sxs-lookup"><span data-stu-id="d7771-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="d7771-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="d7771-104">Step 1.</span></span> <span data-ttu-id="d7771-105">Erstellen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="d7771-105">Creating Certificates</span></span>  
 <span data-ttu-id="d7771-106">Öffnen Sie zum Erstellen eines Zertifikats eine Visual Studio-Eingabeaufforderung mit Administratorrechten, und führen Sie die Datei Setup.bat aus, die in den einzelnen Beispielen enthalten ist, bei denen die sichere Kommunikation über IIS erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d7771-106">To create a certificate for your computer, open a Visual Studio command prompt with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="d7771-107">Stellen Sie vor dem Ausführen dieser Batchdatei sicher, dass der Pfad den Ordner einschließt, in dem sich die Datei Makecert.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="d7771-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="d7771-108">Der folgende Befehl wird zum Erstellen des Zertifikats in Setup.bat verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7771-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="d7771-109">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="d7771-109">Step 2.</span></span> <span data-ttu-id="d7771-110">Installieren von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="d7771-110">Installing Certificates</span></span>  
 <span data-ttu-id="d7771-111">Welche Schritte Sie zum Installieren der erstellten Zertifikate ausführen müssen, hängt von der verwendeten IIS-Version ab.</span><span class="sxs-lookup"><span data-stu-id="d7771-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="d7771-112">Installation mit IIS 5.1 (Windows XP) und IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="d7771-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1.  <span data-ttu-id="d7771-113">Öffnen Sie das MMC-Snap-In Internetinformationsdienste-Manager.</span><span class="sxs-lookup"><span data-stu-id="d7771-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2.  <span data-ttu-id="d7771-114">Mit der rechten Maustaste in die Standardwebsite, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="d7771-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="d7771-115">Wählen Sie die **Verzeichnissicherheit** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="d7771-115">Select the **Directory Security** tab.</span></span>  
  
4.  <span data-ttu-id="d7771-116">Klicken Sie auf die **Serverzertifikat** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d7771-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="d7771-117">Der Assistent für Webserverzertifikate wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="d7771-117">The Web Server Certificate Wizard starts.</span></span>  
  
5.  <span data-ttu-id="d7771-118">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="d7771-118">Complete the wizard.</span></span> <span data-ttu-id="d7771-119">Wählen Sie die Option zum Zuweisen eines Zertifikats aus.</span><span class="sxs-lookup"><span data-stu-id="d7771-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="d7771-120">Wählen Sie aus der angezeigten Liste mit Zertifikaten das Zertifikat ServiceModelSamples-HTTPS-Server aus.</span><span class="sxs-lookup"><span data-stu-id="d7771-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="d7771-121">![IIS-Zertifikat-Assistent](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="d7771-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6.  <span data-ttu-id="d7771-122">Testen Sie den Zugriff auf den Dienst in einem Browser mit der HTTPS-Adresse https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="d7771-122">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="d7771-123">Wenn zuvor SSL mit Httpcfg.exe konfiguriert wurde</span><span class="sxs-lookup"><span data-stu-id="d7771-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1.  <span data-ttu-id="d7771-124">Verwenden Sie zum Erstellen des Serverzertifikats Makecert.exe (oder führen Sie Setup.bat aus).</span><span class="sxs-lookup"><span data-stu-id="d7771-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2.  <span data-ttu-id="d7771-125">Führen Sie den IIS-Manager aus, und installieren Sie das Zertifikat wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d7771-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3.  <span data-ttu-id="d7771-126">Fügen Sie dem Clientprogramm folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="d7771-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7771-127">Dieser Code ist nur für Testzertifikate erforderlich, die z. B. mit Makecert.exe erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d7771-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="d7771-128">Er wird nicht für Produktionsumgebungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d7771-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="d7771-129">Installation mit IIS&#160;7.0 (Windows&#160;Vista und Windows Server&#160;2008)</span><span class="sxs-lookup"><span data-stu-id="d7771-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1.  <span data-ttu-id="d7771-130">Aus der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d7771-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="d7771-131">Mit der rechten Maustaste die **Default Web Site** , und wählen Sie **Bindungen bearbeiten...**</span><span class="sxs-lookup"><span data-stu-id="d7771-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3.  <span data-ttu-id="d7771-132">Klicken Sie auf die **hinzufügen** Schaltfläche der **Sitebindungen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="d7771-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4.  <span data-ttu-id="d7771-133">Wählen Sie **HTTPS** aus der **Typ** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="d7771-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5.  <span data-ttu-id="d7771-134">Wählen Sie die **ServiceModelSamples-HTTPS-Server** aus der **SSL-Zertifikat** Dropdown-Liste und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7771-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6.  <span data-ttu-id="d7771-135">Testen Sie den Zugriff auf den Dienst in einem Browser mit der HTTPS-Adresse https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="d7771-135">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7771-136">Da es sich bei dem gerade installierten Testzertifikat nicht um ein vertrauenswürdiges Zertifikat handelt, werden im Internet Explorer möglicherweise zusätzliche Sicherheitswarnungen angezeigt, wenn Sie zu lokalen Webseiten navigieren, die dieses Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7771-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="d7771-137">Entfernen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="d7771-137">Removing Certificates</span></span>  
  
-   <span data-ttu-id="d7771-138">Führen Sie im Internetinformationsdienste-Manager die zuvor beschriebenen Schritte aus. Entfernen Sie jedoch das Zertifikat bzw. die Bindung, anstatt sie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7771-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
-   <span data-ttu-id="d7771-139">Entfernen Sie das Computerzertifikat mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="d7771-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
