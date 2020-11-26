---
title: XmlSerializer-Fehler
ms.date: 03/30/2017
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
ms.openlocfilehash: 1eefa37d6d11e232bd4d0914eedab3ebb66b92ef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237650"
---
# <a name="xmlserializer-faults"></a>XmlSerializer-Fehler

Im <xref:System.Xml.Serialization.XmlSerializer>-Fehlervertragsbeispiel wird veranschaulicht, wie Fehlerinformationen von einem Dienst zu einem Client mit <xref:System.Xml.Serialization.XmlSerializer> übermittelt werden. Das Beispiel basiert auf den ersten [Schritten, wobei](getting-started-sample.md)zusätzlicher Code zum Dienst hinzugefügt wird, um eine interne Ausnahme in einen Fehler zu konvertieren. Der Client versucht, eine Division durch 0 (null) auszuführen, um einen Fehlerzustand beim Dienst zu erzwingen.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Rechnervertrag wurde geändert, um ein <xref:System.ServiceModel.FaultContractAttribute> einzuschließen, wie im folgenden Beispielcode gezeigt. Darüber hinaus wird das <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet, um die Serialisierung mit <xref:System.Xml.Serialization.XmlSerializer> zu aktivieren. Die <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>-Eigenschaft wird für dieses Attribut auf `true` festgelegt, wodurch das Serialisierungsprogramm angewiesen wird, <xref:System.Xml.Serialization.XmlSerializer> zum Schreiben und Lesen von Fehlern zu verwenden.  
  
```csharp
[XmlSerializerFormat(SupportFaults=true)]  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
  
    [OperationContract]  
    int Subtract(int n1, int n2);  
  
    [OperationContract]  
    int Multiply(int n1, int n2);  
  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 Beim Erstellen von Code für den Client Proxy müssen Sie das **/UseSerializerForFaults** -Flag auf das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)anwenden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
