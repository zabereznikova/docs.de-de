---
title: "Zugriffsautorisierung f&#252;r Dienstvorg&#228;nge | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Autorisierung, Windows Communication Foundation-Beispiel"
  - "Beispiel für Zugriffsautorisierung für Dienstvorgänge [Windows Communication Foundation]"
  - "Dienstverhalten, Beispiel für Zugriffsautorisierung"
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Zugriffsautorisierung f&#252;r Dienstvorg&#228;nge
In diesem Beispiel wird veranschaulicht, wie [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) verwendet wird, um die Verwendung des <xref:System.Security.Permissions.PrincipalPermissionAttribute>\-Attributs für die Zugriffsautorisierung für Dienstvorgänge zu aktivieren.  Dieses Beispiel basiert auf dem Beispiel [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).  Dienst und Client werden mithilfe von [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) konfiguriert.  Das `mode`\-Attribut von [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) wurde auf `Message` und `clientCredentialType` wurde auf `Windows` gesetzt.  <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jede Dienstmethode angewandt und für die Beschränkung des Zugriffs auf jeden Vorgang verwendet.  Der Aufrufer muss Windows\-Administrator sein, um auf jeden Vorgang zugreifen zu können.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS \(Internet Information Services, Internetinformationsdienste\) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Dienstkonfigurationsdatei nutzt [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), um das Attribut `principalPermissionMode`  einzurichten:  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior>  
      ...  
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Die Einrichtung von `principalPermissionMode` auf `UseWindowsGroups` ermöglicht die Verwendung von <xref:System.Security.Permissions.PrincipalPermissionAttribute> basierend auf Windows\-Gruppennamen.  
  
 Das <xref:System.Security.Permissions.PrincipalPermissionAttribute> wird auf jeden Vorgang angewendet, sodass der Aufrufer Mitglied der Windows\-Administratorgruppe sein muss, wie im folgenden Beispielcode gezeigt.  
  
```  
[PrincipalPermission(SecurityAction.Demand,   
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.  Der Client kommuniziert erfolgreich mit jedem Vorgang, wenn er unter einem Konto ausgeführt wird, das zur Administratorgruppe gehört. Andernfalls wird der Zugang verweigert.  Um einen Autorisierungsfehler zu provozieren, führen Sie den Client unter einem Konto aus, das nicht zur Administratorgruppe gehört.  Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
 Ein Dienst kann über Autorisierungsfehler benachrichtigt werden, indem man einen <xref:System.ServiceModel.Dispatcher.IErrorHandler> implementiert.  Weitere Informationen über die Implementierung von `IErrorHandler` finden Sie unter [Erweitern der Kontrolle über Fehlerbehandlung und \-meldung](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md).  
  
### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## Siehe auch