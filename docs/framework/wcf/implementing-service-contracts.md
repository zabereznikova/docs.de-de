---
title: "Implementieren von Dienstvertr&#228;gen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Implementieren von Dienstverträgen [WCF]"
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Implementieren von Dienstvertr&#228;gen
Ein Dienst ist eine Klasse, die die an einem oder mehreren Endpunkten für den Client bereitstehenden Funktionen verfügbar macht.Wenn Sie einen Dienst erstellen möchten, schreiben Sie eine Klasse, die einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\- implementiert.Dazu haben Sie zwei Möglichkeiten:Sie können den Vertrag gesondert als Schnittstelle definieren und dann eine Klasse erstellen, die die Schnittstelle implementiert.Alternativ können Sie die Klasse und den Vertrag direkt erstellen, indem Sie das <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut direkt für die Klasse und das <xref:System.ServiceModel.OperationContractAttribute>\-Attribut für die Methoden festlegen, die für die Clients des Dienstes verfügbar sind.  
  
## Erstellen einer Dienstklasse  
 Im folgende Beispiel implementiert ein Dienst einen  `IMath`\-Vertrag, der gesondert definiert wurde.  
  
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
  
 Ein Dienst kann stattdessen einen Vertrag auch direkt verfügbar machen.Im folgende Beispiel definiert und implementiert eine Dienstklasse einen `MathService`\-Vertrag.  
  
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
  
 Die vorhergehenden Dienste machen hierbei verschiedene Verträge verfügbar, da sich die Vertragsnamen unterscheiden.Im ersten Fall wird der verfügbar gemachte Vertrag "`IMath`" genannt und im zweiten Fall lautet der Name des Vertrags `MathService`".  
  
 Sie können auf den Ebenen der Dienst\- und Vorgangsimplementierung Verschiedenes festlegen, z. B. die Parallelität und Instanziierung.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md).  
  
 Nach der Implementierung eines Dienstvertrags müssen Sie einen oder mehrere Endpunkte für den Dienst erstellen.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Ausführen eines Dienstes finden Sie unter [Hosting\-Dienste](../../../docs/framework/wcf/hosting-services.md).  
  
## Siehe auch  
 [Entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md)   
 [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsklasse](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)   
 [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)   
 [Angeben des Dienstlaufzeitverhaltens](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)