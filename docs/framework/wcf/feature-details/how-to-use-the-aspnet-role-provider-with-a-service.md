---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184767"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst

Der ASP.NET Rollenanbieter (in Verbindung mit dem ASP.NET Mitgliedschaftsanbieter) ist eine Funktion, die es ASP.NET Entwicklern ermöglicht, Websites zu erstellen, die es Benutzern ermöglichen, ein Konto mit einer Website zu erstellen und Rollen für Autorisierungszwecke zugewiesen zu werden. Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmeldeinformationen (die Kombination benutzername/password) bereitstellt, die Website und ihre Dienste verwenden.  
  
Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md). Weitere Informationen zur Funktion des ASP.NET Mitgliedschaftsanbieters finden Sie unter [Gewusst wie: Verwenden des ASP.NET Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).  
  
Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen. Windows Communication Foundation (WCF)-Entwickler können diese Funktionen aus Sicherheitsgründen nutzen. Wenn benutzerin eine WCF-Anwendung integriert ist, müssen sie der WCF-Clientanwendung eine Kombination aus Benutzername und Kennwort bereitstellen. Damit WCF die Datenbank verwenden kann, müssen <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Sie eine <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Instanz <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>der Klasse erstellen, ihre Eigenschaft auf <xref:System.ServiceModel.ServiceHost> festlegen und die Instanz der Auflistung von Verhaltensweisen hinzufügen, die den Dienst hostet.  
  
## <a name="configure-the-role-provider"></a>Konfigurieren des Rollenanbieters  
  
1. Fügen Sie in der Datei Web.config unter `system.web` `roleManager` dem <>-Element ein <>-Element hinzu, und legen Sie dessen `enabled` Attribut auf fest. `true`  
  
2. Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.  
  
3. Fügen Sie als `roleManager` untergeordnetes Element zum `providers` <>-Element ein <>-Element hinzu.  
  
4. Fügen Sie als `providers` untergeordnetes Element zum `add` <>-Element ein <>-Element hinzu, wobei die folgenden Attribute auf die entsprechenden Werte `name`festgelegt sind: , `type`, `connectionStringName`und `applicationName`, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Konfigurieren des Dienstes für die Verwendung des Rollenanbieters  
  
1. Fügen Sie in der Datei Web.config ein [ \<system.serviceModel->-Element](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) hinzu.  
  
2. Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) Sie dem <`system.ServiceModel`>-Element ein Verhalten>Element hinzu.  
  
3. Fügen Sie dem <`behaviors`>-Element einen [ \<serviceBehaviors->](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) hinzu.  
  
4. Fügen [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) Sie ein Verhalten `name`>Element hinzu, und legen Sie das Attribut auf einen geeigneten Wert fest.  
  
5. Fügen Sie dem <`behavior`>-Element einen [ \<serviceAuthorization->](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) hinzu.  
  
6. Legen Sie das `principalPermissionMode`-Attribut auf `UseAspNetRoles` fest.  
  
7. Legen Sie das `roleProviderName`-Attribut auf `SqlRoleProvider` fest. Im folgenden Beispiel wird ein Fragment der Konfiguration dargestellt.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Mitgliedschafts- und Rollenanbieter](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [Gewusst wie: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
