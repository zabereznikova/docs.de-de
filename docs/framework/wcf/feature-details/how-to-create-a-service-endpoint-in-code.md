---
title: 'Vorgehensweise: Erstellen eines Dienstendpunkts im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3fbb22fa-2930-48b8-b437-def1de87c6a0
ms.openlocfilehash: 25ea843df7871d730926fe7b9aac9f21d58e263e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598930"
---
# <a name="how-to-create-a-service-endpoint-in-code"></a>Vorgehensweise: Erstellen eines Dienstendpunkts im Code
In diesem Beispiel wird ein `ICalculator`-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`-Klasse implementiert, und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>-Klasse vom Dienst verwendet werden muss.  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
#### <a name="to-create-a-service-endpoint-in-code"></a>So erstellen Sie einen Dienstendpunkt im Code  
  
1. Erstellen Sie die die Schnittstelle, die den Dienstvertrag definiert.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[c_HowTo_CodeServiceBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Implementieren Sie den in Schritt&#160;1 definierten Dienstvertrag.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[c_HowTo_CodeServiceBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die für den Dienst verwendet werden soll.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[c_HowTo_CodeServiceBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Erstellen Sie den Host, und rufen Sie <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%28System.Type%2CSystem.ServiceModel.Channels.Binding%2CSystem.String%29?displayProperty=nameWithType> oder eine der anderen Überladungen auf, um den Dienstendpunkt dem Host hinzuzufügen.  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#6)]
     [!code-vb[c_HowTo_CodeServiceBinding#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#6)]  
  
     Wenn Sie die Bindung im Code angeben, aber die von der Runtime bereitgestellten Standard Endpunkte verwenden möchten, übergeben Sie beim Erstellen von die Basisadresse in den Konstruktor, <xref:System.ServiceModel.ServiceHost> und geben Sie nicht an <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A?displayProperty=nameWithType> .  
  
     [!code-csharp[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#7)]
     [!code-vb[c_HowTo_CodeServiceBinding#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#7)]  
  
     Weitere Informationen zu Standard Endpunkten finden Sie unter [vereinfachte Konfiguration](../simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Angeben einer Dienstbindung im Code](../how-to-specify-a-service-binding-in-code.md)
