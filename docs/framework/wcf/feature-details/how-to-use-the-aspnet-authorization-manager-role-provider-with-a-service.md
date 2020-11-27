---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: bbdafdd96a32b41d7c6892944ed872e3f8702f0e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280597"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst

Wenn ASP.net einen Webdienst hostet, können Sie den Autorisierungs-Manager in die Anwendung integrieren, um die Autorisierung für den Dienst bereitzustellen. Der Autorisierungs-Manager ermöglicht einem Anwendungsentwickler das Definieren einzelner Vorgänge, die zum Bilden von Aufgaben zusammengruppiert werden können. Ein Administrator kann anschließend Rollen für das Ausführen bestimmter Aufgaben oder einzelner Vorgänge autorisieren. Vom Autorisierungs-Manager wird ein Verwaltungstool als Microsoft Management Console (MMC)-Snap-in für die Verwaltung von Rollen, Aufgaben, Vorgängen und Benutzern zur Verfügung gestellt. Administratoren konfigurieren für den Autorisierungs-Manager einen Richtlinienspeicher in einer XML-Datei, in Active Directory oder in einem ADAM (Active Directory Application Mode)-Speicher.  
  
 Der Autorisierungs-Manager wird in die Anwendung integriert, indem der Autorisierungs-Manager ASP.NET-Rollen Anbieter für die ASP.NET-Anwendung konfiguriert wird, die den Webdienst gehostet. Wie andere ASP.NET-Rollen Anbieter wird der Autorisierungs-Manager ASP.NET-Rollen Anbieter mithilfe des <`providers`>-Elements konfiguriert.  
  
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
  
 Weitere Informationen zum Integrieren eines ASP.NET-Rollen Anbieters in eine WCF-Anwendung finden [Sie unter Gewusst wie: Verwenden des ASP.NET-Rollen Anbieters mit einem-Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md). Weitere Informationen zur Verwendung des Autorisierungs-Managers mit ASP.net finden Sie unter Gewusst [wie: Verwenden des Autorisierungs-Managers (AzMan) mit ASP.NET 2,0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md)
