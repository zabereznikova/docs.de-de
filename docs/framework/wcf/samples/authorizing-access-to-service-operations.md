---
title: "Zugriffsautorisierung für Dienstvorgänge"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2bcd3739cebf852e69cc2551350a83e247274e0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="authorizing-access-to-service-operations"></a>Zugriffsautorisierung für Dienstvorgänge
Dieses Beispiel veranschaulicht, wie die [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) um Verwendung ermöglichen der <xref:System.Security.Permissions.PrincipalPermissionAttribute> Attribut, um den Zugriff auf Dienstvorgänge autorisieren. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) Beispiel. Im Dienst-als auch mit konfiguriert werden die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Die `mode` Attribut von der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) vorsieht `Message` und `clientCredentialType` vorsieht `Windows`. <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jede Dienstmethode angewandt und für die Beschränkung des Zugriffs auf jeden Vorgang verwendet. Der Aufrufer muss Windows-Administrator sein, um auf jeden Vorgang zugreifen zu können.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei verwendet das [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) festzulegende der `principalPermissionMode` Attribut:  
  
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
  
```  
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Der Client kommuniziert erfolgreich mit jedem Vorgang, wenn er unter einem Konto ausgeführt wird, das zur Administratorgruppe gehört. Andernfalls wird der Zugang verweigert. Um einen Autorisierungsfehler zu provozieren, führen Sie den Client unter einem Konto aus, das nicht zur Administratorgruppe gehört. Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
 Ein Dienst kann über Autorisierungsfehler benachrichtigt werden, indem man einen <xref:System.ServiceModel.Dispatcher.IErrorHandler> implementiert. Finden Sie unter [erweitern Steuerelement über Fehlerbehandlung und Berichterstattung](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md) Informationen zur Implementierung `IErrorHandler`.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch
