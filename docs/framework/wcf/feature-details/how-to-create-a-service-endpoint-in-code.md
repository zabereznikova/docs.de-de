---
title: "Gewusst wie: Erstellen eines Dienstendpunkts im Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Gewusst wie: Erstellen eines Dienstendpunkts im Code
In diesem Beispiel wird ein `ICalculator`\-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`\-Klasse implementiert und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>\-Klasse vom Dienst verwendet werden muss.  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da sich die Bindungen und die Adressen eines bereitgestellten Dienstes normalerweise von denen unterscheiden, die während der Entwicklung des Dienstes verwendet wurden.Allgemeiner gesagt ermöglicht das Ausschließen der Bindung und der Adressierungsinformationen aus dem Code ihre Änderung, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
#### So erstellen Sie einen Dienstendpunkt im Code  
  
1.  Erstellen Sie die Schnittstelle, die den Dienstvertrag definiert.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  Implementieren Sie den in Schritt 1 definierten Dienstvertrag.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die für den Dienst verwendet werden soll.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  Erstellen Sie den Host, und rufen Sie <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29> oder eine der anderen Überladungen auf, um den Dienstendpunkt dem Host hinzuzufügen.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     Übergeben Sie beim Erstellen des <xref:System.ServiceModel.ServiceHost> die Basisadresse an den Konstruktor, und rufen Sie nicht <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> auf, um die Bindung im Code anzugeben, aber dabei die Standardendpunkte der Runtime zu verwenden.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Standardendpunkten finden Sie unter [Vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [Vereinfachte Konfiguration für WCF\-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## Siehe auch  
 [Vorgehensweise: Angeben einer Dienstbindung im Code](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md)