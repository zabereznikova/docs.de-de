---
title: Entwrappte Nachrichten
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: edecbc953cd3ade6135b4c76725e65d317d83132
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294977"
---
# <a name="unwrapped-messages"></a>Entwrappte Nachrichten

In diesem Beispiel werden entwrappte Nachrichten veranschaulicht. Standardmäßig wird der Nachrichtentext so formatiert, dass die Parameter zu einem Dienstvorgang eingeschlossen werden. Im folgenden Beispiel wird eine `Add`-Anforderungsnachricht für den `ICalculator`-Dienst im eingeschlossenen Modus gezeigt.  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 Das `<Add>`-Element im Nachrichtentext umschließt den `n1`-Parameter und den `n2`-Parameter. Im Gegensatz dazu wird im folgenden Beispiel die gleiche Nachricht im entwrappten Modus veranschaulicht.  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
```  
  
 Die entwrappte Nachricht schließt den `n1`-Parameter und den `n2`-Parameter nicht in einem einschließenden Element ein, sie sind direkte untergeordnete Elemente des SOAP-Textkörperelements.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird eine entwrappte Nachricht erstellt, indem <xref:System.ServiceModel.MessageContractAttribute> auf den Parametertyp des Dienstvorgangs und den Typ des Rückgabewerts angewendet wird, wie im folgenden Beispielcode dargestellt.  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 Damit Sie die gesendeten und empfangenen Nachrichten anzeigen können, wird in diesem Beispiel die Ablaufverfolgung verwendet. Außerdem wurde <xref:System.ServiceModel.WSHttpBinding> ohne Sicherheit konfiguriert, um die Anzahl der protokollierten Nachrichten zu reduzieren.  
  
 Das resultierende Ablauf Verfolgungs Protokoll (c:\logs\Message.log) kann mit dem [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden. Wählen Sie zum Anzeigen von Nachrichten Inhalten sowohl im linken als auch im rechten Bereich des Service Trace Viewer-Tools **Nachrichten** aus. Ablaufverfolgungsprotokolle in diesem Beispiel sind so konfiguriert, dass sie im Ordner C:\LOGS generiert werden. Erstellen Sie diesen Ordner vor dem Ausführen des Beispiels, und weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Erstellen Sie zum Protokollieren von Nachrichten das Verzeichnis C:\LOGS. Weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.  
  
3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
