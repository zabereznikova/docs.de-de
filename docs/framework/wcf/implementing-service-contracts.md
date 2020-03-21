---
title: Implementieren von Dienstverträgen
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: aefe146a8941d98d7d9138e4ece83c330c967034
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184004"
---
# <a name="implementing-service-contracts"></a>Implementieren von Dienstverträgen
Ein Dienst ist eine Klasse, die die an einem oder mehreren Endpunkten für den Client bereitstehenden Funktionen verfügbar macht. Um einen Dienst zu erstellen, schreiben Sie eine Klasse, die einen Windows Communication Foundation (WCF)-Vertrag implementiert. Dazu haben Sie zwei Möglichkeiten: Sie können den Vertrag gesondert als Schnittstelle definieren und dann eine Klasse erstellen, die die Schnittstelle implementiert. Alternativ können Sie die Klasse und den Vertrag direkt erstellen, indem Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt für die Klasse und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut für die Methoden festlegen, die für die Clients des Dienstes verfügbar sind.  
  
## <a name="creating-a-service-class"></a>Erstellen einer Dienstklasse  
 Im folgende Beispiel implementiert ein Dienst einen  `IMath`-Vertrag, der gesondert definiert wurde.  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Ein Dienst kann stattdessen einen Vertrag auch direkt verfügbar machen. Im folgende Beispiel definiert und implementiert eine Dienstklasse einen `MathService`-Vertrag.  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 Die vorhergehenden Dienste machen hierbei verschiedene Verträge verfügbar, da sich die Vertragsnamen unterscheiden. Im ersten Fall wird der verfügbar gemachte Vertrag "`IMath`" genannt und im zweiten Fall lautet der Name des Vertrags `MathService`".  
  
 Sie können auf den Ebenen der Dienst- und Vorgangsimplementierung Verschiedenes festlegen, z.&#160;B. die Parallelität und Instanziierung. Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Services](designing-and-implementing-services.md).  
  
 Nach der Implementierung eines Dienstvertrags müssen Sie einen oder mehrere Endpunkte für den Dienst erstellen. Weitere Informationen finden Sie unter [Endpoint Creation Overview](endpoint-creation-overview.md). Weitere Informationen zum Ausführen eines Dienstes finden Sie unter [Hostingdienste](hosting-services.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Entwerfen und Implementieren von Diensten](designing-and-implementing-services.md)
- [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsklasse](./feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle](./feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [Angeben des Dienstlaufzeitverhaltens](specifying-service-run-time-behavior.md)
