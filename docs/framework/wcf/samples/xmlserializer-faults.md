---
title: XmlSerializer-Fehler
ms.date: 03/30/2017
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
ms.openlocfilehash: a64a28e7a0105f5133ba2b0cd3abf72d97d5a3e3
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298005"
---
# <a name="xmlserializer-faults"></a>XmlSerializer-Fehler
Im <xref:System.Xml.Serialization.XmlSerializer>-Fehlervertragsbeispiel wird veranschaulicht, wie Fehlerinformationen von einem Dienst zu einem Client mit <xref:System.Xml.Serialization.XmlSerializer> übermittelt werden. Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), wurde dabei zusätzlicher Code hinzugefügt, mit dem Dienst um eine interne Ausnahme in einen Fehler zu konvertieren. Der Client versucht, eine Division durch 0 (null) auszuführen, um einen Fehlerzustand beim Dienst zu erzwingen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
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
  
 Beim Generieren von Code für den Clientproxy müssen Sie Sie anwenden der **/UseSerializerForFaults** flag [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
