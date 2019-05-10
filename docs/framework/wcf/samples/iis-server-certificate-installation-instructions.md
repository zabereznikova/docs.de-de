---
title: Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: 728232c4e1d6309ae0cfacb407417173ece145da
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648353"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="2d705-102">Installationsanleitung für IIS-Serverzertifikate (Internetinformationsdienste)</span><span class="sxs-lookup"><span data-stu-id="2d705-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="2d705-103">Zum Ausführen der Beispiele, die über eine sichere Kommunikation mit Internetinformationsdiensten (IIS) verbunden sind, müssen Sie ein Serverzertifikat erstellen und installieren.</span><span class="sxs-lookup"><span data-stu-id="2d705-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="2d705-104">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="2d705-104">Step 1.</span></span> <span data-ttu-id="2d705-105">Erstellen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2d705-105">Creating Certificates</span></span>  
 <span data-ttu-id="2d705-106">Um ein Zertifikat für den Computer zu erstellen, öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie die Datei Setup.bat aus, die in den einzelnen Beispielen enthalten ist, die sicheren Kommunikation mit IIS zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d705-106">To create a certificate for your computer, open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="2d705-107">Stellen Sie vor dem Ausführen dieser Batchdatei sicher, dass der Pfad den Ordner einschließt, in dem sich die Datei Makecert.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="2d705-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="2d705-108">Der folgende Befehl wird zum Erstellen des Zertifikats in Setup.bat verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d705-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="2d705-109">Schritt 2</span><span class="sxs-lookup"><span data-stu-id="2d705-109">Step 2.</span></span> <span data-ttu-id="2d705-110">Installieren von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2d705-110">Installing Certificates</span></span>  
 <span data-ttu-id="2d705-111">Welche Schritte Sie zum Installieren der erstellten Zertifikate ausführen müssen, hängt von der verwendeten IIS-Version ab.</span><span class="sxs-lookup"><span data-stu-id="2d705-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="2d705-112">Installation mit IIS 5.1 (Windows XP) und IIS 6.0 (Windows Server 2003)</span><span class="sxs-lookup"><span data-stu-id="2d705-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1. <span data-ttu-id="2d705-113">Öffnen Sie das MMC-Snap-In Internetinformationsdienste-Manager.</span><span class="sxs-lookup"><span data-stu-id="2d705-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2. <span data-ttu-id="2d705-114">Mit der rechten Maustaste die Standardwebsite, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2d705-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3. <span data-ttu-id="2d705-115">Wählen Sie die **Verzeichnissicherheit** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="2d705-115">Select the **Directory Security** tab.</span></span>  
  
4. <span data-ttu-id="2d705-116">Klicken Sie auf die **Serverzertifikat** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="2d705-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="2d705-117">Der Assistent für Webserverzertifikate wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="2d705-117">The Web Server Certificate Wizard starts.</span></span>  
  
5. <span data-ttu-id="2d705-118">Durchlaufen Sie den Assistenten.</span><span class="sxs-lookup"><span data-stu-id="2d705-118">Complete the wizard.</span></span> <span data-ttu-id="2d705-119">Wählen Sie die Option zum Zuweisen eines Zertifikats aus.</span><span class="sxs-lookup"><span data-stu-id="2d705-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="2d705-120">Wählen Sie aus der angezeigten Liste mit Zertifikaten das Zertifikat ServiceModelSamples-HTTPS-Server aus.</span><span class="sxs-lookup"><span data-stu-id="2d705-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="2d705-121">![IIS-Zertifikat-Assistent](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="2d705-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6. <span data-ttu-id="2d705-122">Testen Sie den Zugriff auf den Dienst unter Verwendung der HTTPS-Adresse in einem Browser `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="2d705-122">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="2d705-123">Wenn zuvor SSL mit Httpcfg.exe konfiguriert wurde</span><span class="sxs-lookup"><span data-stu-id="2d705-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1. <span data-ttu-id="2d705-124">Verwenden Sie zum Erstellen des Serverzertifikats Makecert.exe (oder führen Sie Setup.bat aus).</span><span class="sxs-lookup"><span data-stu-id="2d705-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2. <span data-ttu-id="2d705-125">Führen Sie den IIS-Manager aus, und installieren Sie das Zertifikat wie oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d705-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3. <span data-ttu-id="2d705-126">Fügen Sie dem Clientprogramm folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d705-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d705-127">Dieser Code ist nur für Testzertifikate erforderlich, die z. B. mit Makecert.exe erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2d705-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="2d705-128">Er wird nicht für Produktionsumgebungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2d705-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="2d705-129">Installation mit IIS&amp;#160;7.0 (Windows&amp;#160;Vista und Windows Server&amp;#160;2008)</span><span class="sxs-lookup"><span data-stu-id="2d705-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1. <span data-ttu-id="2d705-130">Von der **starten** Menü klicken Sie auf **ausführen**, geben Sie dann **Inetmgr** auf das Internet Information Services (IIS)-MMC-Snap-in zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2d705-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="2d705-131">Mit der rechten Maustaste die **Default Web Site** , und wählen Sie **Bindungen bearbeiten...**</span><span class="sxs-lookup"><span data-stu-id="2d705-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3. <span data-ttu-id="2d705-132">Klicken Sie auf die **hinzufügen** -Schaltfläche der **Sitebindungen** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="2d705-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4. <span data-ttu-id="2d705-133">Wählen Sie **HTTPS** aus der **Typ** Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="2d705-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5. <span data-ttu-id="2d705-134">Wählen Sie die **ServiceModelSamples-HTTPS-Server** aus der **SSL-Zertifikat** Dropdown-Liste und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d705-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6. <span data-ttu-id="2d705-135">Testen Sie den Zugriff auf den Dienst unter Verwendung der HTTPS-Adresse in einem Browser `https://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="2d705-135">Test access to the service in a browser by using the HTTPS address `https://localhost/servicemodelsamples/service.svc`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d705-136">Da es sich bei dem gerade installierten Testzertifikat nicht um ein vertrauenswürdiges Zertifikat handelt, werden im Internet Explorer möglicherweise zusätzliche Sicherheitswarnungen angezeigt, wenn Sie zu lokalen Webseiten navigieren, die dieses Zertifikat verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d705-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="2d705-137">Entfernen von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2d705-137">Removing Certificates</span></span>  
  
- <span data-ttu-id="2d705-138">Führen Sie im Internetinformationsdienste-Manager die zuvor beschriebenen Schritte aus. Entfernen Sie jedoch das Zertifikat bzw. die Bindung, anstatt sie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2d705-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
- <span data-ttu-id="2d705-139">Entfernen Sie das Computerzertifikat mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="2d705-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
