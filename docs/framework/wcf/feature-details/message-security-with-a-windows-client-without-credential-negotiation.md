---
title: "Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
caps.latest.revision: 18
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 18
---
# Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung
Das folgende Szenario zeigt einen durch das Kerberos\-Protokoll gesicherten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client und \-Dienst.  
  
 Sowohl der Dienst als auch der Client befinden sich in der gleichen Domäne bzw. in den gleichen vertrauenswürdigen Domänen.  
  
> [!NOTE]
>  Der Unterschied zwischen diesem Szenario und [Nachrichtensicherheit über einen Windows\-Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) besteht darin, dass in diesem Szenario vor dem Senden der Anwendungsnachricht keine Aushandlung der Dienstanmeldeinformationen mit dem Dienst stattfindet.  Da hierzu das Kerberos\-Protokoll erforderlich ist, muss für dieses Szenario auch eine Windows\-Domänenumgebung vorhanden sein.  
  
 ![Nachrichtensicherheit ohne Aushandlung von Anmeldeinformationen](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa\-2439\-4ef9\-92f4\-43c242d85d0d")  
  
|Merkmal|Beschreibung|  
|-------------|------------------|  
|Sicherheitsmodus|Meldung|  
|Interoperabilität|Ja, WS\-Security mit Clients mit Kerberos\-Tokenprofilkompatibilität|  
|Authentifizierung \(Server\)|Gegenseitige Authentifizierung des Servers und des Clients|  
|Authentifizierung \(Client\)|Gegenseitige Authentifizierung des Servers und des Clients|  
|Integrität|Ja|  
|Vertraulichkeit|Ja|  
|Transport|HTTP|  
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|  
  
## Dienst  
 Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.  Führen Sie einen der folgenden Schritte aus:  
  
-   Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.  
  
-   Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.  
  
### Code  
 Der folgende Code dient zum Erstellen eines Dienstendpunkts mit Nachrichtensicherheit.  Mit diesem Code wird das Aushandeln der Dienstanmeldeinformationen sowie das Einrichten eines Sicherheitskontexttokens \(Security Context Token, SCT\) deaktiviert.  
  
> [!NOTE]
>  Zur Verwendung des Windows\-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Diensts Zugriff auf den bei der Active Directory\-Domäne registrierten Dienstprinzipalnamen \(Service Principal Name, SPN\) haben.  Dazu gibt es zwei Möglichkeiten:  
  
1.  Verwenden Sie das `NetworkService`\-Konto oder das `LocalSystem`\-Konto, um den Dienst auszuführen.  Da diese Konten über Zugriff auf den beim Hinzufügen des Computers zur Active Directory\-Domäne erstellten Computer\-SPN verfügen, wird von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatisch das entsprechende SPN\-Element im Endpunkt des Diensts in den Dienstmetadaten \(Web Services Description Language, WSDL\) generiert.  
  
2.  Verwenden Sie ein beliebiges Active Directory\-Domänenkonto, um den Dienst auszuführen.  In diesem Fall muss für das Domänenkonto ein SPN eingerichtet werden.  Eine mögliche Vorgehensweise hierzu besteht in der Verwendung des Tools Setspn.exe.  Konfigurieren Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach dem Erstellen des SPNs für das Konto so, dass dieser SPN für die Clients des Diensts über seine Metadaten \(WSDL\) veröffentlicht wird.  Legen Sie hierzu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.  Im folgenden Beispiel wird die Identität programmgesteuert veröffentlicht:  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] über SPNs, das Kerberos\-Protokoll und Active Directory finden Sie unter [Technische Kerberos\-Ergänzung für Windows](http://go.microsoft.com/fwlink/?LinkId=88330).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Endpunktidentitäten finden Sie unter [SecurityBindingElement\-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### Konfiguration  
 Anstelle des Codes kann die folgende Konfiguration verwendet werden:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## Client  
 Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.  Führen Sie einen der folgenden Schritte aus:  
  
-   Erstellen Sie mit dem Code \(und Clientcode\) einen eigenständigen Client.  
  
-   Erstellen Sie einen Client, der keine Endpunktadressen definiert.  Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.  Beispiel:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### Code  
 Der folgende Code dient zum Konfigurieren des Clients.  Der Sicherheitsmodus ist auf Nachrichtensicherheit, der Typ der Clientanmeldeinformationen auf Windows festgelegt.  Die Eigenschaften <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> und <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> sind auf `false` festgelegt.  
  
> [!NOTE]
>  Zur Verwendung des Windows\-Anmeldeinformationstyps ohne Aushandlung muss der Client vor dem Starten der Kommunikation mit dem Dienst mit dem Konto\-SPN des Diensts konfiguriert werden.  Der SPN wird vom Client zum Abrufen des Kerberos\-Tokens verwendet, um damit die Kommunikation mit dem Dienst zu authentifizieren und zu sichern.  Im folgenden Beispiel wird das Konfigurieren des Clients mit dem SPN des Diensts veranschaulicht.  Wenn [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren des Clients verwendet wird, wird der SPN des Diensts aus den Dienstmetadaten \(WSDL\) automatisch an den Client weitergegeben, sofern diese Information in den Metadaten des Diensts enthalten ist.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Konfigurieren des Diensts, sodass der SPN in die Dienstmetadaten aufgenommen wird, finden Sie weiter unten in diesem Thema im Abschnitt "Dienst".  
>   
>  Weitere Informationen über SPNs, Kerberos und Active Directory finden Sie unter [Technische Kerberos\-Ergänzung für Windows](http://go.microsoft.com/fwlink/?LinkId=88330).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Endpunktidentitäten finden Sie unter dem Thema [SecurityBindingElement\-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### Konfiguration  
 Der folgende Code dient zum Konfigurieren des Clients.  Das [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md)\-Element muss so festgelegt werden, dass es dem für das Dienstkonto in der Active Directory\-Domäne registrierten Dienst\-SPN entspricht.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)