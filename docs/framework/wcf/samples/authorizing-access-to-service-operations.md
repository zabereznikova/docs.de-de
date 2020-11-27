---
title: Zugriffsautorisierung für Dienstvorgänge
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: 68e6d53b656cb6327487598f65fa4f04c2495292
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255454"
---
# <a name="authorizing-access-to-service-operations"></a>Zugriffsautorisierung für Dienstvorgänge

In diesem Beispiel wird veranschaulicht, wie verwendet wird, um [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) die Verwendung des- <xref:System.Security.Permissions.PrincipalPermissionAttribute> Attributs zum Autorisieren des Zugriffs auf Dienst Vorgänge zu aktivieren. Dieses Beispiel basiert auf dem Beispiel " [Getting Started](getting-started-sample.md) ". Der Dienst und der Client werden mithilfe von konfiguriert [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . Das `mode` -Attribut von wurde [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) auf festgelegt, `Message` und wurde `clientCredentialType` auf festgelegt `Windows` . <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jede Dienstmethode angewandt und für die Beschränkung des Zugriffs auf jeden Vorgang verwendet. Der Aufrufer muss Windows-Administrator sein, um auf jeden Vorgang zugreifen zu können.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienst Konfigurationsdatei verwendet zum [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) Festlegen des- `principalPermissionMode` Attributs das-Attribut:  
  
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
  
 Ein Dienst kann über Autorisierungsfehler benachrichtigt werden, indem man einen <xref:System.ServiceModel.Dispatcher.IErrorHandler> implementiert. Informationen zum Implementieren von finden Sie unter [Erweitern der Kontrolle über Fehlerbehandlung und Bericht](extending-control-over-error-handling-and-reporting.md) Erstellung `IErrorHandler` .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
