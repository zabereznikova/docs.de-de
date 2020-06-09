---
title: Nachrichtensicherheit – Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: 7b5b9ba0cc9a6d867b0478720b6151c7a561da16
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584713"
---
# <a name="message-security-windows"></a>Nachrichtensicherheit – Windows
In diesem Beispiel wird veranschaulicht, wie eine <xref:System.ServiceModel.WSHttpBinding>-Bindung konfiguriert wird, um mit Windows-Authentifizierung Sicherheit auf Nachrichtenebene zu verwenden. Dieses Beispiel basiert [auf den ersten](getting-started-sample.md)Schritten. In diesem Beispiel wird der Dienst in Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Standard Sicherheit für [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ist die Nachrichten Sicherheit mithilfe der Windows-Authentifizierung. In den Konfigurationsdateien in diesem Beispiel wird das `mode` -Attribut von explizit [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) auf `Message` und das- `clientCredentialType` Attribut auf `Windows` festgelegt. Diese Werte sind die Standardwerte für diese Bindung, wurden allerdings, wie in der folgenden Beispielkonfiguration zur Veranschaulichung ihrer Verwendung, explizit konfiguriert.  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Die Clientbindung wird mit dem entsprechenden `securityMode` und `authenticationMode` konfiguriert.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"
            binding="wsHttpBinding"
            bindingConfiguration="Binding1"
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Der Quellcode für den Dienst wurde geändert, um zu veranschaulichen, wie <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> verwendet werden kann, um auf die Identität des Aufrufers zuzugreifen.  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Die erste aufgerufene Methode – `GetCallerIdentity` – gibt den Namen der Identität des Aufrufers zurück an den Client. Drücken Sie im Konsolenfenster die EINGABETASTE, um den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
