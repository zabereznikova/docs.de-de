---
title: "Vorgehensweise: Verwenden des Rollenanbieters f&#252;r den ASP.NET bei einem Dienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Verwenden des Rollenanbieters f&#252;r den ASP.NET bei einem Dienst
Der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Rollenanbieter \(zusammen mit dem [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Mitgliedschaftsanbieter\) ist eine Funktion für [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Entwickler zum Erstellen von Websites, mit denen die Benutzer ein Konto auf einer Site erstellen können. Außerdem können ihnen Rollen für die Autorisierung zugewiesen werden.Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden.Dies steht im Gegensatz zur Windows\-Sicherheit, bei der die Benutzer über Konten in einer Windows\-Domäne verfügen müssen.Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen \(eine Kombination aus Benutzername\/Kennwort\) angibt, die Site und ihre Dienste nutzen.  
  
 Eine Beispielanwendung finden Sie unter [Mitgliedschafts\- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Mitgliedschaftsanbieterfunktion finden Sie unter [Gewusst wie: Verwenden des ASP.NET\-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
 Die Rollenanbieterfunktion verwendet eine SQL Server\-Datenbank zum Speichern von Benutzerinformationen.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Entwickler können diese Funktionen für Sicherheitszwecke nutzen.Wenn sie in eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Anwendung integriert sind, müssen die Benutzer der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientanwendung eine Kombination aus Benutzername\/Kennwort bereitstellen.Damit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Datenbank verwenden kann, müssen Sie eine Instanz der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>\-Klasse erstellen, ihre <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A>\-Eigenschaft auf <xref:System.ServiceModel.Description.PrincipalPermissionMode> festlegen und die Instanz zu der Verhaltensauflistung zum <xref:System.ServiceModel.ServiceHost> hinzufügen, der den Dienst hostet.  
  
### So konfigurieren Sie den Rollenanbieter  
  
1.  Fügen Sie in der Datei Web.config unter dem \<`system.web`\>\-Element ein \<`roleManager`\>\-Element hinzu, und legen Sie das `enabled`\-Attribut auf `true` fest.  
  
2.  Legen Sie das `defaultProvider`\-Attribut auf `SqlRoleProvider` fest.  
  
3.  Fügen Sie ein \<`providers`\>\-Element als untergeordnetes Element des \<`roleManager`\>\-Elements hinzu.  
  
4.  Fügen Sie ein \<`add`\>\-Element als untergeordnetes Element zum \<`providers`\>\-Element hinzu, wobei die folgenden Attribute auf die entsprechenden Werte festgelegt werden sollten: `name`, `type`, `connectionStringName` und `applicationName`, wie im folgenden Beispiel dargestellt.  
  
    ```  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### So konfigurieren Sie den Dienst für die Verwendung des Rollenanbieters  
  
1.  Fügen Sie in der Datei Web.config ein [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Element hinzu.  
  
2.  Fügen Sie dem \<`system.ServiceModel`\>\-Element ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)Element hinzu.  
  
3.  Fügen Sie dem \<`behaviors`\>\-Element ein [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)\-Element hinzu.  
  
4.  Fügen Sie ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)\-Element hinzu, und legen Sie das `name`\-Attribut auf einen passenden Wert fest.  
  
5.  Fügen Sie dem \<`behavior`\>\-Element ein [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)\-Element hinzu.  
  
6.  Legen Sie das `principalPermissionMode`\-Attribut auf `UseAspNetRoles` fest.  
  
7.  Legen Sie das `roleProviderName`\-Attribut auf `SqlRoleProvider` fest.Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.  
  
    ```  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## Siehe auch  
 [Mitgliedschafts\- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)   
 [Gewusst wie: Verwenden des ASP.NET\-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)