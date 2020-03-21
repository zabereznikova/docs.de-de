---
title: Zugriffsautorisierung für Dienstvorgänge
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: c2ad6977674666ef65df1ea4cfe58cfd4bff8b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183927"
---
# <a name="authorizing-access-to-service-operations"></a>Zugriffsautorisierung für Dienstvorgänge
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Security.Permissions.PrincipalPermissionAttribute> [ \<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) verwendet wird, um die Verwendung des Attributs zum Autorisieren des Zugriffs auf Dienstvorgänge zu aktivieren. Dieses Beispiel basiert auf dem Beispiel [Erste Schritte.](../../../../docs/framework/wcf/samples/getting-started-sample.md) Der Dienst und der Client werden mit dem [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)konfiguriert. Das `mode` Attribut [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) der>wurde `Message` auf `clientCredentialType` festgelegt und `Windows`auf festgelegt. <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jede Dienstmethode angewandt und für die Beschränkung des Zugriffs auf jeden Vorgang verwendet. Der Aufrufer muss Windows-Administrator sein, um auf jeden Vorgang zugreifen zu können.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei verwendet die `principalPermissionMode` [ \<serviceAuthorization>,](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) um das Attribut zu setzen:  
  
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
  
 Ein Dienst kann über Autorisierungsfehler benachrichtigt werden, indem man einen <xref:System.ServiceModel.Dispatcher.IErrorHandler> implementiert. Weitere Informationen zum Implementieren `IErrorHandler`finden Sie unter Erweitern der Steuerung über [Fehlerbehandlung und -berichterstattung.](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Einzel- oder Computerkonfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
