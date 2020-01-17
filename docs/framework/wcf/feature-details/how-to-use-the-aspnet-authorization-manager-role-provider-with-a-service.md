---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 20955578ce4d344c2057036c0944557edf737389
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212223"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst
Wenn ASP.net einen Webdienst hostet, können Sie den Autorisierungs-Manager in die Anwendung integrieren, um die Autorisierung für den Dienst bereitzustellen. Der Autorisierungs-Manager ermöglicht einem Anwendungsentwickler das Definieren einzelner Vorgänge, die zum Bilden von Aufgaben zusammengruppiert werden können. Ein Administrator kann anschließend Rollen für das Ausführen bestimmter Aufgaben oder einzelner Vorgänge autorisieren. Vom Autorisierungs-Manager wird ein Verwaltungstool als Microsoft Management Console (MMC)-Snap-in für die Verwaltung von Rollen, Aufgaben, Vorgängen und Benutzern zur Verfügung gestellt. Administratoren konfigurieren für den Autorisierungs-Manager einen Richtlinienspeicher in einer XML-Datei, in Active Directory oder in einem ADAM (Active Directory Application Mode)-Speicher.  
  
 Der Autorisierungs-Manager wird in die Anwendung integriert, indem der Autorisierungs-Manager ASP.NET-Rollen Anbieter für die ASP.NET-Anwendung konfiguriert wird, die den Webdienst gehostet. Wie andere ASP.NET-Rollen Anbieter wird der Autorisierungs-Manager ASP.NET-Rollen Anbieter mit dem <`providers`>-Element konfiguriert.  
  
 Das folgende Codebeispiel ist ein Teil einer Konfigurationsdatei für einen Webdienst, der den Autorisierungs-Manager in die Anwendung integriert.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Weitere Informationen zum Integrieren eines ASP.NET-Rollen Anbieters in eine WCF-Anwendung finden [Sie unter Gewusst wie: Verwenden des ASP.NET-Rollen Anbieters mit einem-Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Weitere Informationen zur Verwendung des Autorisierungs-Managers mit ASP.net finden Sie unter Gewusst [wie: Verwenden des Autorisierungs-Managers (AzMan) mit ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
