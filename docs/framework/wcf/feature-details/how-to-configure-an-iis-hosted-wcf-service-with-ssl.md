---
title: 'Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cb6a0b7913434be70efdc5af780980b971b5bc6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a><span data-ttu-id="bcad0-102">Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL</span><span class="sxs-lookup"><span data-stu-id="bcad0-102">How to: Configure an IIS-hosted WCF service with SSL</span></span>
<span data-ttu-id="bcad0-103">In diesem Thema wird beschrieben, wie ein von IIS gehosteter WCF-Dienst für die Verwendung der HTTP-Transportsicherheit eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="bcad0-103">This topic describes how to set up an IIS-hosted WCF service to use HTTP transport security.</span></span> <span data-ttu-id="bcad0-104">Die HTTP-Transportsicherheit erfordert für die Registrierung bei IIS ein SSL-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bcad0-104">HTTP transport security requires an SSL certificate to be registered with IIS.</span></span> <span data-ttu-id="bcad0-105">Wenn Sie über kein SSL-Zertifikat verfügen, können Sie mit IIS ein Testzertifikat generieren.</span><span class="sxs-lookup"><span data-stu-id="bcad0-105">If you do not have an SSL certificate you can use IIS to generate a test certificate.</span></span> <span data-ttu-id="bcad0-106">Danach müssen Sie der Website eine SSL-Bindung hinzufügen und die Authentifizierungseigenschaften der Website konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bcad0-106">Next you must add an SSL binding to the web site and configure the web site’s authentication properties.</span></span> <span data-ttu-id="bcad0-107">Abschließend müssen Sie den WCF-Dienst für die Verwendung von HTTPS konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bcad0-107">Finally you need to configure the WCF service to use HTTPS.</span></span>  
  
### <a name="creating-a-self-signed-certificate"></a><span data-ttu-id="bcad0-108">Erstellen eines selbstsignierten Zertifikats</span><span class="sxs-lookup"><span data-stu-id="bcad0-108">Creating a Self-Signed Certificate</span></span>  
  
1.  <span data-ttu-id="bcad0-109">Öffnen Sie den Internetinformationsdienste-Manager (inetmgr.exe), und wählen Sie in der linken Strukturansicht den Computernamen aus.</span><span class="sxs-lookup"><span data-stu-id="bcad0-109">Open Internet Information Services Manager (inetmgr.exe), and select your computer name in the left-hand tree view.</span></span> <span data-ttu-id="bcad0-110">Wählen Sie auf der rechten Seite des Bildschirms Serverzertifikate aus.</span><span class="sxs-lookup"><span data-stu-id="bcad0-110">On the right-hand side of the screen select Server Certificates</span></span>  
  
     <span data-ttu-id="bcad0-111">![Startbildschirm des IIS-Manager](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "Mg_INetMgrHome")</span><span class="sxs-lookup"><span data-stu-id="bcad0-111">![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")</span></span>  
  
2.  <span data-ttu-id="bcad0-112">Klicken Sie im Fenster Zertifikate auf den **selbstsigniertes Zertifikat erstellen...**</span><span class="sxs-lookup"><span data-stu-id="bcad0-112">In the Server Certificates window click the **Create Self-Signed Certificate….**</span></span> <span data-ttu-id="bcad0-113">Link.</span><span class="sxs-lookup"><span data-stu-id="bcad0-113">Link.</span></span>  
  
     <span data-ttu-id="bcad0-114">![Erstellen einer Self &#45; signiertes Zertifikat mit IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "Mg_CreateSelfSignedCert")</span><span class="sxs-lookup"><span data-stu-id="bcad0-114">![Creating a self&#45;signed certificate with IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")</span></span>  
  
3.  <span data-ttu-id="bcad0-115">Geben Sie einen Anzeigenamen für das selbstsignierte Zertifikat, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcad0-115">Enter a friendly name for the self-signed certificate and click **OK**.</span></span>  
  
     <span data-ttu-id="bcad0-116">![Erstellen Sie Self-Service &#45; Dialogfeld "Zertifikat" signiert](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "Mg_MyCert")</span><span class="sxs-lookup"><span data-stu-id="bcad0-116">![Create Self&#45;Signed Certificate Dialog](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "mg_MyCert")</span></span>  
  
     <span data-ttu-id="bcad0-117">Die Details des neu erstellten selbstsignierten Zertifikats werden nun angezeigt, der **Serverzertifikate** Fenster.</span><span class="sxs-lookup"><span data-stu-id="bcad0-117">The newly created self-signed certificate details are now shown in the **Server Certificates** window.</span></span>  
  
     <span data-ttu-id="bcad0-118">![Fenster "Serverzertifikat" Server](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "Mg_ServerCertificateWindow")</span><span class="sxs-lookup"><span data-stu-id="bcad0-118">![Server Certificate Window](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")</span></span>  
  
     <span data-ttu-id="bcad0-119">Das generierte Zertifikat wird im Speicher für vertrauenswürdige Stammzertifizierungsstellen installiert.</span><span class="sxs-lookup"><span data-stu-id="bcad0-119">The generated certificate is installed in the Trusted Root Certification Authorities store.</span></span>  
  
### <a name="add-ssl-binding"></a><span data-ttu-id="bcad0-120">Hinzufügen einer SSL-Bindung</span><span class="sxs-lookup"><span data-stu-id="bcad0-120">Add SSL Binding</span></span>  
  
1.  <span data-ttu-id="bcad0-121">Erweitern Sie im Internetinformationsdienste-Manager, der **Sites** Ordner und dann die **Default Web Site** Ordner in der Strukturansicht auf der linken Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="bcad0-121">Still in Internet Information Services Manager, expand the **Sites** folder and then the **Default Web Site** folder in the tree view on the left-hand side of the screen.</span></span>  
  
2.  <span data-ttu-id="bcad0-122">Klicken Sie auf die **Bindungen...**</span><span class="sxs-lookup"><span data-stu-id="bcad0-122">Click the **Bindings….**</span></span> <span data-ttu-id="bcad0-123">Verknüpfen Sie der **Aktionen** Abschnitt im rechten oberen Bereich des Fensters.</span><span class="sxs-lookup"><span data-stu-id="bcad0-123">Link in the **Actions** section in the upper right hand portion of the window.</span></span>  
  
     <span data-ttu-id="bcad0-124">![Hinzufügen einer SSL-Bindung](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "Mg_AddSSLBinding")</span><span class="sxs-lookup"><span data-stu-id="bcad0-124">![Adding an SSL binding](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "mg_AddSSLBinding")</span></span>  
  
3.  <span data-ttu-id="bcad0-125">Klicken Sie im Fenster Sitebindungen auf dem **hinzufügen** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="bcad0-125">In the Site Bindings window click the **Add** button.</span></span>  
  
     <span data-ttu-id="bcad0-126">![Dialogfeld "Sitebindungen" Site](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "Mg_SiteBindingsDialog")</span><span class="sxs-lookup"><span data-stu-id="bcad0-126">![Site Bindings Dialog](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")</span></span>  
  
4.  <span data-ttu-id="bcad0-127">In der **Sitebindung hinzufügen** Dialogfeld Wählen Sie Https für den Typ und den Anzeigenamen des selbstsignierten Zertifikats, das Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bcad0-127">In the **Add Site Binding** dialog, select https for the type and the friendly name of the self-signed certificate you just created.</span></span>  
  
     <span data-ttu-id="bcad0-128">![Beispiel für sitebindung](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "Mg_MyCertBinding")</span><span class="sxs-lookup"><span data-stu-id="bcad0-128">![Site binding example](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "mg_MyCertBinding")</span></span>  
  
### <a name="configure-virtual-directory-for-ssl"></a><span data-ttu-id="bcad0-129">Konfigurieren eines virtuellen Verzeichnisses für SSL</span><span class="sxs-lookup"><span data-stu-id="bcad0-129">Configure Virtual Directory for SSL</span></span>  
  
1.  <span data-ttu-id="bcad0-130">Wählen Sie im Internetinformationsdienste-Manager das virtuelle Verzeichnis aus, das den sicheren WCF-Dienst enthält.</span><span class="sxs-lookup"><span data-stu-id="bcad0-130">Still in Internet Information Services Manager, select the virtual directory that contains your WCF secure service.</span></span>  
  
2.  <span data-ttu-id="bcad0-131">Wählen Sie im mittleren Bereich des Fensters **SSL-Einstellungen** im IIS-Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="bcad0-131">In the center pane of the window, select **SSL Settings** in the IIS section.</span></span>  
  
     <span data-ttu-id="bcad0-132">![SSL-Einstellungen für virtuelles Verzeichnis](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "Mg_SSLSettingsForVDir")</span><span class="sxs-lookup"><span data-stu-id="bcad0-132">![SSL Settings for virtual directory](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")</span></span>  
  
3.  <span data-ttu-id="bcad0-133">Die SSL-Einstellungen wählen Sie im Bereich der **SSL erforderlich** Kontrollkästchen und klicken Sie auf der **übernehmen** link in der **Aktionen** Abschnitt auf der rechten Seite des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="bcad0-133">In the SSL Settings pane, select the **Require SSL** checkbox and click the **Apply** link in the **Actions** section on the right hand side of the screen.</span></span>  
  
     <span data-ttu-id="bcad0-134">![SSL-Einstellungen für virtuelle Verzeichnisse](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "Mg_VDirSSLSettings")</span><span class="sxs-lookup"><span data-stu-id="bcad0-134">![Virtual directory SSL settings](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")</span></span>  
  
### <a name="configure-wcf-service-for-http-transport-security"></a><span data-ttu-id="bcad0-135">Konfigurieren des WCF-Dienstes für HTTP-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="bcad0-135">Configure WCF Service for HTTP Transport Security</span></span>  
  
1.  <span data-ttu-id="bcad0-136">Konfigurieren Sie in der Datei web.config des WCF-Diensts die HTTP-Bindung für die Verwendung der Transportsicherheit, wie im folgenden XML-Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bcad0-136">In the WCF service’s web.config configure the HTTP binding to use transport security as shown in the following XML.</span></span>  
  
    ```xml  
    <bindings>  
          <basicHttpBinding>  
            <binding name="secureHttpBinding">  
              <security mode="Transport">  
                <transport clientCredentialType="None"/>  
              </security>  
            </binding>  
          </basicHttpBinding>  
    </bindings>  
    ```  
  
2.  <span data-ttu-id="bcad0-137">Geben Sie den Dienst und Dienstendpunkt an, wie im folgenden XML-Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcad0-137">Specify your service and service endpoint as shown in the following XML.</span></span>  
  
    ```xml  
    <services>  
          <service name="MySecureWCFService.Service1">  
            <endpoint address=""  
                      binding="basicHttpBinding"  
                      bindingConfiguration="secureHttpBinding"  
                      contract="MySecureWCFService.IService1"/>  
  
            <endpoint address="mex"  
                      binding="mexHttpsBinding"  
                      contract="IMetadataExchange" />  
          </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="bcad0-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcad0-138">Example</span></span>  
 <span data-ttu-id="bcad0-139">Im Folgenden finden Sie ein vollständiges Beispiel für die Datei web.config eines WCF-Diensts, der HTTP-Transportsicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcad0-139">The following is a complete example of a web.config file for a WCF service using HTTP transport security</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
  
  <system.web>  
    <compilation debug="true" targetFramework="4.0" />  
  </system.web>  
  <system.serviceModel>  
    <services>  
      <service name="MySecureWCFService.Service1">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="secureHttpBinding"  
                  contract="MySecureWCFService.IService1"/>  
  
        <endpoint address="mex"  
                  binding="mexHttpsBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="secureHttpBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <!-- To avoid disclosing metadata information, set the value below to false and remove the metadata endpoint above before deployment -->  
          <serviceMetadata httpsGetEnabled="true"/>  
          <!-- To receive exception details in faults for debugging purposes, set the value below to true.  Set to false before deployment to avoid disclosing exception information -->  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <serviceHostingEnvironment multipleSiteBindingsEnabled="true" />  
  </system.serviceModel>  
  <system.webServer>  
    <modules runAllManagedModulesForAllRequests="true"/>  
  </system.webServer>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcad0-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcad0-140">See Also</span></span>  
 [<span data-ttu-id="bcad0-141">Hosten in Internetinformationsdienste (IIS)</span><span class="sxs-lookup"><span data-stu-id="bcad0-141">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="bcad0-142">Internet-Internetinformationsdiensts</span><span class="sxs-lookup"><span data-stu-id="bcad0-142">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)  
 [<span data-ttu-id="bcad0-143">Internetinformation Services Hosting bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="bcad0-143">Internet Information Services Hosting Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [<span data-ttu-id="bcad0-144">IIS-Hosting mithilfe von Inlinecode</span><span class="sxs-lookup"><span data-stu-id="bcad0-144">IIS Hosting Using Inline Code</span></span>](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
