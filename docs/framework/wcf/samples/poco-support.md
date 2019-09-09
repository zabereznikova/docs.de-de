---
title: POCO-Unterstützung
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: 6796d7948bd3ebe0a8b96a861c628b30b7540912
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044780"
---
# <a name="poco-support"></a>POCO-Unterstützung
In diesem Beispiel wird die Serialisierungsunterstützung für makellose Typen demonstriert, d.&#160;h. Typen, auf die Serialisierungsattribute nicht angewendet wurden (diese werden auch als POCO-Typen (Plain Old CLR Object) bezeichnet). Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag für alle öffentlichen, nicht markierten Typen ab, die über einen Parameter losen Konstruktor verfügen. Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen. Weitere Informationen zu nicht markierten Typen finden Sie unter [serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Dieses Beispiel basiert auf den ersten [Schritten, verwendet jedoch komplexe](../../../../docs/framework/wcf/samples/getting-started-sample.md)Zahlen anstelle von primitiven numerischen Typen. Es ähnelt auch dem Beispiel für den [grundlegenden Datenvertrag](../../../../docs/framework/wcf/samples/basic-data-contract.md) , mit der <xref:System.Runtime.Serialization.DataContractAttribute> Ausnahme <xref:System.Runtime.Serialization.DataMemberAttribute> , dass das-Attribut und das-Attribut nicht verwendet werden.  
  
 Der Dienst wird von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die `ComplexNumber`-Klasse wird im `ServiceContract` verwendet. Der `ComplexNumber`-Typ verfügt nicht über das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut, wie im folgenden Beispielcode dargestellt. Standardmäßig werden alle öffentlichen Eigenschaften und Felder serialisiert.  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)
