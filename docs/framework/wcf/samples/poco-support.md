---
title: POCO-Unterstützung
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: e94f6d9576ed96613d975a66c1965820002f94ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183419"
---
# <a name="poco-support"></a>POCO-Unterstützung
In diesem Beispiel wird die Serialisierungsunterstützung für makellose Typen demonstriert, d.&#160;h. Typen, auf die Serialisierungsattribute nicht angewendet wurden (diese werden auch als POCO-Typen (Plain Old CLR Object) bezeichnet). Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag für alle öffentlichen nicht markierten Typen ab, die über einen parameterlosen Konstruktor verfügen. Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen. Weitere Informationen zu nicht markierten Typen finden Sie unter [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Dieses Beispiel basiert auf den [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), verwendet jedoch komplexe Zahlen anstelle primitiver numerischer Typen. Es ähnelt auch dem [Beispiel "Basic Data Contract",](../../../../docs/framework/wcf/samples/basic-data-contract.md) mit der Ausnahme, dass die <xref:System.Runtime.Serialization.DataContractAttribute> und-Attribute <xref:System.Runtime.Serialization.DataMemberAttribute> nicht verwendet werden.  
  
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
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)
