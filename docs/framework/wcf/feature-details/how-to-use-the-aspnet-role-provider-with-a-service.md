---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 45eeda046e877b4379d7d0e5edd90fac305f5e44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595296"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst

Der ASP.NET-Rollen Anbieter (in Verbindung mit dem ASP.net-Mitgliedschafts Anbieter) ist ein Feature, mit dem ASP.NET-Entwickler Websites erstellen können, die Benutzern das Erstellen eines Kontos mit einer Website und das Zuweisen von Rollen zu Autorisierungs Zwecken ermöglichen. Jeder Benutzer kann mit dieser Funktion ein Konto auf dieser Site erstellen und sich für den exklusiven Zugriff auf diese Site und ihre Dienste anmelden. Dies steht im Gegensatz zur Windows-Sicherheit, bei der die Benutzer über Konten in einer Windows-Domäne verfügen müssen. Stattdessen kann jeder Benutzer, der seine Anmelde Informationen (die Kombination aus Benutzername und Kennwort) bereitstellt, die Website und seine Dienste verwenden.  
  
Eine Beispielanwendung finden Sie unter [Mitgliedschaft und Rollen Anbieter](../samples/membership-and-role-provider.md). Weitere Informationen zur ASP.net-Mitgliedschafts Anbieter Funktion finden Sie unter Gewusst [wie: Verwenden des ASP.net-Mitgliedschafts Anbieters](how-to-use-the-aspnet-membership-provider.md).  
  
Die Rollenanbieterfunktion verwendet eine SQL Server-Datenbank zum Speichern von Benutzerinformationen. Windows Communication Foundation (WCF)-Entwickler können diese Features aus Sicherheitsgründen nutzen. Wenn Benutzer in eine WCF-Anwendung integriert sind, müssen Sie der WCF-Client Anwendung eine Kombination aus Benutzername und Kennwort bereitstellen. Um WCF die Verwendung der Datenbank zu ermöglichen, müssen Sie eine Instanz der- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> Klasse erstellen, deren- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> Eigenschaft auf festlegen <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> und die-Instanz der Auflistung von Verhalten hinzufügen, die <xref:System.ServiceModel.ServiceHost> den-Dienst gehostet.  
  
## <a name="configure-the-role-provider"></a>Konfigurieren des Rollen Anbieters  
  
1. Fügen Sie in der Datei Web. config unter dem < `system.web` >-Element ein < `roleManager` >-Element hinzu, und legen Sie dessen- `enabled` Attribut auf fest `true` .  
  
2. Legen Sie das `defaultProvider`-Attribut auf `SqlRoleProvider` fest.  
  
3. Fügen Sie als untergeordnetes Element des <`roleManager`>-Elements ein <`providers`>-Element hinzu.  
  
4. Fügen Sie als untergeordnetes Element des <`providers`>-Elements ein <`add`> Element mit den folgenden Attributen hinzu, die auf die entsprechenden Werte festgelegt sind: `name` , `type` , `connectionStringName` und `applicationName` , wie im folgenden Beispiel gezeigt.  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Konfigurieren Sie den Dienst für die Verwendung des Rollen Anbieters.  
  
1. Fügen Sie in der Datei Web. config ein- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) Element hinzu.  
  
2. Fügen Sie [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) dem <>-Element ein-Element hinzu `system.ServiceModel` .  
  
3. Fügen Sie ein- [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) Element zum <`behaviors`>-Element hinzu.  
  
4. Fügen Sie ein [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) -Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest  
  
5. Fügen Sie ein- [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) Element zum <`behavior`>-Element hinzu.  
  
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

- [Mitgliedschafts- und Rollenanbieter](../samples/membership-and-role-provider.md)
- [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](how-to-use-the-aspnet-membership-provider.md)
