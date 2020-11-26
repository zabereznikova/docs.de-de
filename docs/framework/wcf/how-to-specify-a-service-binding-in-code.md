---
title: 'Vorgehensweise: Angeben einer Dienstbindung im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236480"
---
# <a name="how-to-specify-a-service-binding-in-code"></a>Vorgehensweise: Angeben einer Dienstbindung im Code

In diesem Beispiel wird ein `ICalculator`-Vertrag für einen Rechnerdienst definiert, der Dienst wird in der `CalculatorService`-Klasse implementiert, und der Endpunkt wird im Code definiert. Dort ist angegeben, dass die <xref:System.ServiceModel.BasicHttpBinding>-Klasse vom Dienst verwendet werden muss.  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
 Eine Beschreibung der Konfiguration dieses Dienstanbieter mithilfe von Konfigurationselementen anstelle von Code finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](how-to-specify-a-service-binding-in-configuration.md).  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a>So geben Sie im Code die Verwendung der BasicHttpBinding für den Dienst an  
  
1. Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Implementieren Sie den Dienstvertrag in einer Dienstklasse.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. Erstellen Sie in der Hostanwendung eine Basisadresse für den Dienst und die Bindung, die mit dem Dienst verwendet werden soll.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Erstellen Sie den Host für den Dienst, fügen Sie den Endpunkt hinzu, und öffnen Sie den Host.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a>So ändern Sie die Standardwerte für die Bindungseigenschaften  
  
1. Um die Standardeigenschaftswerte der <xref:System.ServiceModel.BasicHttpBinding>-Klasse zu ändern, legen Sie den Eigenschaftswert für die Bindung auf den neuen Wert fest, bevor Sie den Host erstellen. Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, verwenden Sie den folgenden Code:  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
- [Angeben einer Endpunktadresse](specifying-an-endpoint-address.md)
