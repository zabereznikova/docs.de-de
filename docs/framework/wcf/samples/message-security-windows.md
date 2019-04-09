---
title: Nachrichtensicherheit – Windows
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: fd70fbf4983819cc017b98e3c4b17a9010460ccb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078056"
---
# <a name="message-security-windows"></a>Nachrichtensicherheit – Windows
In diesem Beispiel wird veranschaulicht, wie eine <xref:System.ServiceModel.WSHttpBinding>-Bindung konfiguriert wird, um mit Windows-Authentifizierung Sicherheit auf Nachrichtenebene zu verwenden. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md). In diesem Beispiel wird der Dienst in Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die Standardsicherheit für die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) ist nachrichtensicherheit, die mithilfe der Windows-Authentifizierung. Die Konfigurationsdateien in diesem Beispiel explizit festlegen der `mode` Attribut der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) zu `Message` und die `clientCredentialType` -Attribut auf `Windows`. Diese Werte sind die Standardwerte für diese Bindung, wurden allerdings, wie in der folgenden Beispielkonfiguration zur Veranschaulichung ihrer Verwendung, explizit konfiguriert.  
  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
