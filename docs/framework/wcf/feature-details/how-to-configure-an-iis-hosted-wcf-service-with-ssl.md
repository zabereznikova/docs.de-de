---
title: 'Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL'
description: Erfahren Sie, wie Sie einen IIS-gehosteten WCF-Dienst einrichten, um die HTTP-Transportsicherheit zu verwenden. hierfür ist ein Zertifikat erforderlich, das bei IIS registriert ist.
ms.date: 03/30/2017
ms.assetid: df2fe31f-a4bb-4024-92ca-b74ba055e038
ms.openlocfilehash: 960005761d3bed917142141976e9f9094094b34c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257651"
---
# <a name="how-to-configure-an-iis-hosted-wcf-service-with-ssl"></a>Vorgehensweise: Konfigurieren eines IIS-gehosteten WCF-Diensts mit SSL

In diesem Thema wird beschrieben, wie ein von IIS gehosteter WCF-Dienst für die Verwendung der HTTP-Transportsicherheit eingerichtet wird. Die HTTP-Transportsicherheit erfordert für die Registrierung bei IIS ein SSL-Zertifikat. Wenn Sie über kein SSL-Zertifikat verfügen, können Sie mit IIS ein Testzertifikat generieren. Danach müssen Sie der Website eine SSL-Bindung hinzufügen und die Authentifizierungseigenschaften der Website konfigurieren. Abschließend müssen Sie den WCF-Dienst für die Verwendung von HTTPS konfigurieren.  
  
### <a name="creating-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats  
  
1. Öffnen Sie den Internetinformationsdienste-Manager (inetmgr.exe), und wählen Sie in der linken Strukturansicht den Computernamen aus. Wählen Sie auf der rechten Seite des Bildschirms Serverzertifikate aus.  
  
     ![Hauptbildschirm von IIS-Manager](media/mg-inetmgrhome.jpg "mg_INetMgrHome")  
  
2. Klicken Sie im Fenster Server Zertifikate auf das **Self-Signed Zertifikat erstellen....** Verknüpfen.  
  
     ![Erstellen eines selbst&#45;signierten Zertifikats mit IIS](media/mg-createselfsignedcert.jpg "mg_CreateSelfSignedCert")  
  
3. Geben Sie einen anzeigen Amen für das selbst signierte Zertifikat ein, und klicken Sie auf **OK**.  
  
     ![Dialog Feld "selbst&#45;signiertes Zertifikat erstellen"](media/mg-mycert.jpg "mg_MyCert")  
  
     Die neu erstellten selbst signierten Zertifikat Details werden nun im Fenster **Server Zertifikate** angezeigt.  
  
     ![Fenster "Serverzertifikat"](media/mg-servercertificatewindow.jpg "mg_ServerCertificateWindow")  
  
     Das generierte Zertifikat wird im Speicher für vertrauenswürdige Stammzertifizierungsstellen installiert.  
  
### <a name="add-ssl-binding"></a>Hinzufügen einer SSL-Bindung  
  
1. Erweitern Sie in Internetinformationsdienste-Manager den Ordner **Sites** und dann den **Standardordner Website** in der Strukturansicht auf der linken Seite des Bildschirms.  
  
2. Klicken Sie auf **Bindungen....** Link im Abschnitt " **Aktionen** " im oberen rechten Bereich des Fensters.  
  
     ![Hinzufügen einer SSL-Bindung](media/mg-addsslbinding.jpg "mg_AddSSLBinding")  
  
3. Klicken Sie im Fenster Site Bindungen auf die Schaltfläche **Hinzufügen** .  
  
     ![Dialogfeld "Sitebindungen"](media/mg-sitebindingsdialog.jpg "mg_SiteBindingsDialog")  
  
4. Wählen Sie im Dialogfeld **Site Bindung hinzufügen** HTTPS für den Typ und den anzeigen amen des selbst signierten Zertifikats aus, das Sie soeben erstellt haben.  
  
     ![Beispiel für Sitebindung](media/mg-mycertbinding.jpg "mg_MyCertBinding")  
  
### <a name="configure-virtual-directory-for-ssl"></a>Konfigurieren eines virtuellen Verzeichnisses für SSL  
  
1. Wählen Sie im Internetinformationsdienste-Manager das virtuelle Verzeichnis aus, das den sicheren WCF-Dienst enthält.  
  
2. Wählen Sie im mittleren Fensterbereich im Abschnitt IIS die Option **SSL-Einstellungen** aus.  
  
     ![SSL-Einstellungen für virtuelles Verzeichnis](media/mg-sslsettingsforvdir.jpg "mg_SSLSettingsForVDir")  
  
3. Aktivieren Sie im Bereich SSL-Einstellungen das Kontrollkästchen **SSL erforderlich** , und klicken Sie im Abschnitt **Aktionen** auf der rechten Seite des Bildschirms auf den Link **anwenden** .  
  
     ![SSL-Einstellungen für virtuelles Verzeichnis](media/mg-vdirsslsettings.JPG "mg_VDirSSLSettings")  
  
### <a name="configure-wcf-service-for-http-transport-security"></a>Konfigurieren des WCF-Dienstes für HTTP-Transportsicherheit  
  
1. Konfigurieren Sie in der Datei web.config des WCF-Diensts die HTTP-Bindung für die Verwendung der Transportsicherheit, wie im folgenden XML-Code dargestellt.  
  
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
  
2. Geben Sie den Dienst und Dienstendpunkt an, wie im folgenden XML-Code gezeigt.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten in Internetinformationsdiensten](hosting-in-internet-information-services.md)
- [Hostinganweisungen des Internetinformationsdiensts](../samples/internet-information-service-hosting-instructions.md)
- [Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten](internet-information-services-hosting-best-practices.md)
- [IIS-Hosting mithilfe von Inlinecode](../samples/iis-hosting-using-inline-code.md)
