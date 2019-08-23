---
title: Zugriffsautorisierung für Dienstvorgänge
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: a0ea82c876b3bd8c2a3218f84399fbb69e1d0080
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932499"
---
# <a name="authorizing-access-to-service-operations"></a>Zugriffsautorisierung für Dienstvorgänge
Dieses Beispiel veranschaulicht, wie die [ \<ServiceAuthorization->](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) verwendet wird, um die <xref:System.Security.Permissions.PrincipalPermissionAttribute> Verwendung des-Attributs zum Autorisieren des Zugriffs auf Dienst Vorgänge zu aktivieren. Dieses Beispiel basiert auf dem Beispiel " [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) ". Der Dienst und der Client werden mithilfe der [ \<WSHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)konfiguriert. Das `mode` `Message` -Attribut `Windows` `clientCredentialType` [ \<des Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) wurde auf festgelegt, und wurde auf festgelegt. <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jede Dienstmethode angewandt und für die Beschränkung des Zugriffs auf jeden Vorgang verwendet. Der Aufrufer muss Windows-Administrator sein, um auf jeden Vorgang zugreifen zu können.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienst Konfigurationsdatei verwendet die [ \<ServiceAuthorization->](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) , `principalPermissionMode` um das-Attribut festzulegen:  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>   
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Die Einrichtung von `principalPermissionMode` auf `UseWindowsGroups` ermöglicht die Verwendung von <xref:System.Security.Permissions.PrincipalPermissionAttribute> basierend auf Windows-Gruppennamen.  
  
 Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jeden Vorgang angewendet, sodass der Aufrufer Mitglied der Windows-Administratorgruppe sein muss, wie im folgenden Beispielcode gezeigt.  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Der Client kommuniziert erfolgreich mit jedem Vorgang, wenn er unter einem Konto ausgeführt wird, das zur Administratorgruppe gehört. Andernfalls wird der Zugang verweigert. Um einen Autorisierungsfehler zu provozieren, führen Sie den Client unter einem Konto aus, das nicht zur Administratorgruppe gehört. Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
 Ein Dienst kann über Autorisierungsfehler benachrichtigt werden, indem man einen <xref:System.ServiceModel.Dispatcher.IErrorHandler> implementiert. Informationen zum Implementieren `IErrorHandler`von finden Sie unter [Erweitern der Kontrolle über Fehlerbehandlung und Bericht](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) Erstellung.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
