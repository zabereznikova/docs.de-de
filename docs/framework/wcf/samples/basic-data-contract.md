---
title: Grundlegender Datenvertrag
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Data Contract
ms.assetid: b124e9e0-cb73-4ae0-b9c3-e6cdf5eced98
caps.latest.revision: "37"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: adba148a6e61437ba4e4089efb7a77efe3a785a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="basic-data-contract"></a>Grundlegender Datenvertrag
In diesem Beispiel wird das Implementieren eines Datenvertrags veranschaulicht. Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) aber verwendet komplexe Zahlen anstelle von grundlegenden numerischen Typen.  
  
 In diesem Beispiel wird der Dienst von Internetinformationsdiensten (IIS) gehostet, und der Client ist eine Konsolenanwendung (.exe).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Dienstvertrag für diesen Dienst verwendet komplexe Zahlen, wie im folgenden Beispielcode gezeigt.  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 Das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut wurden auf die Definition der `ComplexNumber`-Klasse angewendet, um anzugeben, welche Felder der Klasse zwischen dem Client und dem Dienst übertragen werden können, wie im folgenden Beispielcode dargestellt.  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class ComplexNumber  
{  
    [DataMember]  
    public double Real = 0.0D;  
    [DataMember]  
    public double Imaginary = 0.0D;  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
 Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück. Dabei werden Zahlen vom Typ `ComplexNumber` akzeptiert und zurückgegeben.  
  
```  
// This is the service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
  
    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real - n2.Real, n1.Imaginary -   
                                                     n2.Imaginary);  
    }  
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)  
    {  
        double real1 = n1.Real * n2.Real;  
        double imaginary1 = n1.Real * n2.Imaginary;  
        double imaginary2 = n2.Real * n1.Imaginary;  
        double real2 = n1.Imaginary * n2.Imaginary * -1;  
        return new ComplexNumber(real1 + real2, imaginary1 +   
                                                 imaginary2);  
    }  
  
    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)  
    {  
         ComplexNumber conjugate =   
              new ComplexNumber(n2.Real, -1*n2.Imaginary);  
         ComplexNumber numerator = Multiply(n1, conjugate);  
         ComplexNumber denominator = Multiply(n2, conjugate);  
         return new ComplexNumber(numerator.Real / denominator.Real,  
                                               numerator.Imaginary);  
    }  
}  
```  
  
 Die Clientimplementierung verwendet ebenfalls komplexe Zahlen. Der Dienstvertrag und den Datenvertrag sind in der Quelle Datei "generatedclient.cs", die von generiert wird definiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus Dienstmetadaten.  
  
```  
// Create a client.  
DataContractCalculatorClient client = new DataContractCalculatorClient();  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();   
value1.Real = 1;   
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();   
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = proxy.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
      value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
      result.Real, result.Imaginary);   
    …  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten des Vorgangs im Konsolenfenster des Clients angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i  
  
Press <ENTER> to terminate client.  
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
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`  
  
## <a name="see-also"></a>Siehe auch
