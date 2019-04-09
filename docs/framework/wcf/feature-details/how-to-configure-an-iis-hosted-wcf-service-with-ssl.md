---
title: 'Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL'
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 336c3800fc033cc12bd9c3fe168ae219b72cab91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214117"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL
In diesem Thema wird beschrieben, wie ein von IIS gehosteter WCF-Dienst für die Verwendung der HTTP-Transportsicherheit eingerichtet wird. Die HTTP-Transportsicherheit erfordert für die Registrierung bei IIS ein SSL-Zertifikat. Wenn Sie über kein SSL-Zertifikat verfügen, können Sie mit IIS ein Testzertifikat generieren. Danach müssen Sie der Website eine SSL-Bindung hinzufügen und die Authentifizierungseigenschaften der Website konfigurieren. Abschließend müssen Sie den WCF-Dienst für die Verwendung von HTTPS konfigurieren.  
  
### <a name="creating-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats  
  
1.  Öffnen Sie den Internetinformationsdienste-Manager (inetmgr.exe), und wählen Sie in der linken Strukturansicht den Computernamen aus. Wählen Sie auf der rechten Seite des Bildschirms Serverzertifikate aus.  
  
     ![IIS Manager Home Screen](../../../../docs/framework/wcf/feature-details/media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2.  Klicken Sie im Fenster Serverzertifikate auf das **selbstsigniertes Zertifikat erstellen...** Link.  
  
     ![Erstellen ein selbstsigniertes&#45;selbstsignierten Zertifikats mit IIS](../../../../docs/framework/wcf/feature-details/media/mg-createselfsignedcert.jpg "Mg_CreateSelfSignedCert")  
  
3.  Geben Sie einen Anzeigenamen für das selbstsignierte Zertifikat, und klicken Sie auf **OK**.  
  
     ![Erstellen Sie Self-Service&#45;Dialogfeld "Zertifikat" signiert](../../../../docs/framework/wcf/feature-details/media/mg-mycert.jpg "Mg_MyCert")  
  
     Die Details des neu erstellten selbstsignierten Zertifikats werden jetzt angezeigt, der **Serverzertifikate** Fenster.  
  
     ![Server-Fenster "Serverzertifikat"](../../../../docs/framework/wcf/feature-details/media/mg-servercertificatewindow.jpg "Mg_ServerCertificateWindow")  
  
     Das generierte Zertifikat wird im Speicher für vertrauenswürdige Stammzertifizierungsstellen installiert.  
  
### <a name="add-ssl-binding"></a>Hinzufügen einer SSL-Bindung  
  
1.  Noch im Internetinformationsdienste-Manager, erweitern Sie die **Websites** Ordner und klicken Sie dann die **Default Web Site** Ordner in der Strukturansicht auf der linken Seite des Bildschirms.  
  
2.  Klicken Sie auf die **Bindungen...** -Link in der **Aktionen** Abschnitt in der rechten oberen Bereich des Fensters.  
  
     ![Hinzufügen einer SSL-Bindung](../../../../docs/framework/wcf/feature-details/media/mg-addsslbinding.jpg "Mg_AddSSLBinding")  
  
3.  Klicken Sie im Fenster "Websitebindungen" auf die **hinzufügen** Schaltfläche.  
  
     ![Dialogfeld "Sitebindungen" Site](../../../../docs/framework/wcf/feature-details/media/mg-sitebindingsdialog.jpg "Mg_SiteBindingsDialog")  
  
4.  In der **Sitebindung hinzufügen** Dialogfeld Option Https für den Typ und den Anzeigenamen des das selbstsignierte Zertifikat, das Sie gerade erstellt haben.  
  
     ![Beispiel für sitebindung](../../../../docs/framework/wcf/feature-details/media/mg-mycertbinding.jpg "Mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Konfigurieren eines virtuellen Verzeichnisses für SSL  
  
1.  Wählen Sie im Internetinformationsdienste-Manager das virtuelle Verzeichnis aus, das den sicheren WCF-Dienst enthält.  
  
2.  Wählen Sie im mittleren Bereich des Fensters **SSL-Einstellungen** im IIS-Abschnitt.  
  
     ![SSL-Einstellungen für virtuelles Verzeichnis](../../../../docs/framework/wcf/feature-details/media/mg-sslsettingsforvdir.jpg "Mg_SSLSettingsForVDir")  
  
3.  Wählen Sie im Bereich SSL-Einstellungen der **SSL erforderlich** Kontrollkästchen und klicken Sie auf die **übernehmen** -link in der **Aktionen** Abschnitt auf der rechten Seite des Bildschirms.  
  
     ![SSL-Einstellungen des virtuellen Verzeichnisses](../../../../docs/framework/wcf/feature-details/media/mg-vdirsslsettings.JPG "Mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Konfigurieren des WCF-Dienstes für HTTP-Transportsicherheit  
  
1.  Konfigurieren Sie in der Datei web.config des WCF-Diensts die HTTP-Bindung für die Verwendung der Transportsicherheit, wie im folgenden XML-Code dargestellt.  
  
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
  
2.  Geben Sie den Dienst und Dienstendpunkt an, wie im folgenden XML-Code gezeigt.  
  
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
  
## <a name="example"></a>Beispiel  
 Im Folgenden finden Sie ein vollständiges Beispiel für die Datei web.config eines WCF-Diensts, der HTTP-Transportsicherheit verwendet.  
  
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
  
## <a name="see-also"></a>Siehe auch

- [Hosten in Internetinformationsdiensten](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [Hostinganweisungen des Internetinformationsdiensts](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
- [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [IIS-Hosting mithilfe von Inlinecode](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)
