---
title: 'Vorgehensweise: Angeben einer Clientbindung im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: 9be571d7be020aef546fdd7ec7cb7519a48ea350
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184056"
---
# <a name="how-to-specify-a-client-binding-in-code"></a>Vorgehensweise: Angeben einer Clientbindung im Code
In diesem Beispiel wird ein Client erstellt, um einen Rechnerdienst zu nutzen, und die Bindung des Clients wird imperativ im Code angegeben. Der Client greift auf den `CalculatorService` zu, der die `ICalculator`-Schnittstelle implementiert, und sowohl der Dienst als auch der Client verwenden die Klasse <xref:System.ServiceModel.BasicHttpBinding>.  
  
 In dieser Prozedur wird davon ausgegangen, dass der Rechnerdienst ausgeführt wird. Informationen zum Erstellen des Dienstes finden Sie unter [Gewusst wie: Angeben einer Dienstbindung in Konfiguration](how-to-specify-a-service-binding-in-configuration.md). Es verwendet auch das [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) bietet, um automatisch die Clientkomponenten zu generieren. Das Tool generiert den Clientcode für den Zugriff auf den Dienst.  
  
 Der Client wird in zwei Schritten erstellt. Svcutil.exe generiert den `ClientCalculator`, der die `ICalculator`-Schnittstelle implementiert. Anschließend wird die Clientanwendung erstellt, indem eine Instanz von `ClientCalculator` erstellt wird und dann die Bindung und die Adresse für den Dienst im Code angegeben werden.  
  
 Die Quellkopie dieses Beispiels finden Sie im [BasicBinding-Beispiel.](./samples/basicbinding.md)  
  
### <a name="to-specify-a-custom-binding-in-code"></a>So geben Sie eine benutzerdefinierte Bindung im Code an  
  
1. Verwenden Sie Svcutil.exe in der Befehlszeile, um Code von Dienstmetadaten zu generieren.  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. Der generierte Client enthält außerdem die Implementierung vom `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. Erstellen Sie eine Instanz des `ClientCalculator`, der die <xref:System.ServiceModel.BasicHttpBinding>-Klasse in einer Clientanwendung verwendet, und rufen Sie anschließend die Dienstvorgänge an der angegebenen Adresse auf.  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. Kompilieren Sie den Code, und führen Sie den Client aus.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
