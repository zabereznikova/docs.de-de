---
title: "Vorgehensweise: Angeben einer Dienstbindung im Code | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Angeben einer Dienstbindung im Code
In diesem Beispiel wird ein `ICalculator`\-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`\-Klasse implementiert, und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>\-Klasse vom Dienst verwendet werden muss.  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code.Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da sich die Bindungen und die Adressen eines bereitgestellten Dienstes normalerweise von denen unterscheiden, die während der Entwicklung des Dienstes verwendet wurden.Allgemeiner gesagt ermöglicht das Ausschließen der Bindung und der Adressierungsinformationen aus dem Code, sie zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
 Eine Beschreibung der Konfiguration des Diensts mit Konfigurationselementen anstelle von Code finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).  
  
### So geben Sie im Code die Verwendung der BasicHttpBinding für den Dienst an  
  
1.  Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2.  Implementieren Sie den Dienstvertrag in einer Dienstklasse.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3.  Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die mit dem Dienst verwendet werden soll.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4.  Erstellen Sie den Host für den Dienst, fügen Sie den Endpunkt hinzu, und öffnen Sie den Host.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### So ändern Sie die Standardwerte für die Bindungseigenschaften  
  
1.  Um die Standardeigenschaftswerte der <xref:System.ServiceModel.BasicHttpBinding>\-Klasse zu ändern, legen Sie den Eigenschaftswert für die Bindung auf den neuen Wert fest, bevor Sie den Host erstellen.Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, verwenden Sie den folgenden Code:  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## Siehe auch  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md)