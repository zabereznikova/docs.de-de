---
title: "Vorgehensweise: Deklarieren von Fehlern in Dienstvertr&#228;gen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vorgehensweise: Deklarieren von Fehlern in Dienstvertr&#228;gen
In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.  Im Gegensatz dazu werden in [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen mittels Dienstverträgen die an Clients zurückzugebenden Fehlerinformationen angegeben. Zu diesem Zweck werden SOAP\-Fehler in den Dienstverträgen deklariert.  Eine Übersicht über die Beziehung zwischen Ausnahmen und Fehlern finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
### Erstellen eines Dienstvertrags zum Angeben eines SOAP\-Fehlers  
  
1.  Erstellen Sie einen Dienstvertrag, der mindestens einen Vorgang enthält.  Ein Beispiel finden Sie unter [Gewusst wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Wählen Sie einen Vorgang aus, der sich zum Angeben einer Fehlerbedingung eignet, aufgrund derer die Clients eine entsprechende Benachrichtigung erhalten.  Eine Entscheidungshilfe für die Auswahl von Fehlerbedingungen, die das Zurückgeben eines SOAP\-Fehlers an Clients rechtfertigen, finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
3.  Wenden Sie ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName> auf den ausgewählten Vorgang an, und geben Sie einen serialisierbaren Fehlertyp an den Konstruktor weiter.  Weitere Informationen zum Erstellen und Verwenden serialisierbarer Typen finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).  Im folgenden Beispiel wird gezeigt, wie angegeben werden kann, dass der `SampleMethod`\-Vorgang zu einem `GreetingFault` führt.  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  Wiederholen Sie die Schritte 2 und 3 für alle Vorgänge des Vertrags, durch die Fehlerbedingungen an Clients weitergegeben werden.  
  
## Implementieren eines Vorgangs für das Zurückgeben eines angegebenen SOAP\-Fehlers  
 Nachdem für einen Vorgang angegeben wurde, dass ein bestimmter SOAP\-Fehler zurückgegeben werden kann, um eine Fehlerbedingung an eine aufrufende Anwendung weiterzugeben \(wie beispielsweise in der vorangehenden Prozedur beschrieben\), besteht der nächste Schritt in der Implementierung dieser Angabe.  
  
#### Auslösen des angegebenen SOAP\-Fehlers im Vorgang  
  
1.  Tritt in einem Vorgang eine durch <xref:System.ServiceModel.FaultContractAttribute> angegebene Fehlerbedingung auf, lösen Sie eine neue <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> aus. Der angegebene SOAP\-Fehler fungiert hierbei als Typparameter.  Im folgenden Beispiel wird gezeigt, wie der `GreetingFault` in der im vorherigen Abschnitt gezeigten `SampleMethod` sowie im folgenden Codeabschnitt ausgelöst werden kann.  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## Beispiel  
 Das folgende Codebeispiel zeigt die Implementierung eines Einzelvorgangs, durch den ein `GreetingFault` für den `SampleMethod`\-Vorgang angegeben wird.  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## Siehe auch  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.FaultException%601?displayProperty=fullName>