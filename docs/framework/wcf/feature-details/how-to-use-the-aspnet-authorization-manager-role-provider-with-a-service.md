---
title: 'Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst'
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: c21c1a80468bd81f2df69009afd2be86ee714250
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331708"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst
Wird von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] ein Webdienst gehostet, kann der Autorisierungs-Manager in die Anwendung integriert werden, um dem Dienst Autorisierung zu gewähren. Der Autorisierungs-Manager ermöglicht einem Anwendungsentwickler das Definieren einzelner Vorgänge, die zum Bilden von Aufgaben zusammengruppiert werden können. Ein Administrator kann anschließend Rollen für das Ausführen bestimmter Aufgaben oder einzelner Vorgänge autorisieren. Vom Autorisierungs-Manager wird ein Verwaltungstool als Microsoft Management Console (MMC)-Snap-in für die Verwaltung von Rollen, Aufgaben, Vorgängen und Benutzern zur Verfügung gestellt. Administratoren konfigurieren für den Autorisierungs-Manager einen Richtlinienspeicher in einer XML-Datei, in Active Directory oder in einem ADAM (Active Directory Application Mode)-Speicher.  
  
 Der Autorisierungs-Manager wird durch Konfigurieren des [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieters des Autorisierungs-Managers für die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung, die als Host für den Webdienst fungiert, in die Anwendung integriert. Wie andere [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter wird der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Rollenanbieter des Autorisierungs-Managers mithilfe des <`providers`>-Elements konfiguriert.  
  
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
  
 Weitere Informationen zur Integration einer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] -Rollenanbieters in eine WCF-Anwendung finden Sie unter [wie: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md). Weitere Informationen zur Verwendung des Autorisierungs-Managers mit [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], finden Sie unter [Vorgehensweise: Use Authorization Manager (AzMan) mit ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
