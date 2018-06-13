---
title: POCO-Unterstützung
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: ab95469afa53bd0b27efc451875d4912db74a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501985"
---
# <a name="poco-support"></a>POCO-Unterstützung
In diesem Beispiel wird die Serialisierungsunterstützung für makellose Typen demonstriert, d.&#160;h. Typen, auf die Serialisierungsattribute nicht angewendet wurden (diese werden auch als POCO-Typen (Plain Old CLR Object) bezeichnet). Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag für alle öffentlichen makellosen Typen ab, die über einen Standardkonstruktor verfügen. Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen. Weitere Informationen zum nicht markierten Typen finden Sie unter [serialisierbaren Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), aber verwendet komplexe Zahlen anstelle von primitiven numerischen Typen. Es ist auch ähnelt der [grundlegenden Datenvertrag](../../../../docs/framework/wcf/samples/basic-data-contract.md) -Beispiel, außer dass die <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> Attribute werden nicht verwendet.  
  
 Der Dienst wird von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die `ComplexNumber`-Klasse wird im `ServiceContract` verwendet. Der `ComplexNumber`-Typ verfügt nicht über das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut, wie im folgenden Beispielcode dargestellt. Standardmäßig werden alle öffentlichen Eigenschaften und Felder serialisiert.  
  
```  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)
