---
title: 'Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: c0022e6ce3a63c1f497eeee82ca959cec1046cec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490151"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag
Eine Funktion von Windows Communication Foundation (WCF), ist die Fähigkeit zum Erstellen eines Diensts, das ein duplexnachrichtenmuster verwendet. Anhand dieses Musters kann ein Dienst mit dem Client über einen Rückruf kommunizieren In diesem Thema wird gezeigt, die Schritte zum Erstellen von eines WCF-Clients in einer Clientklasse, die die Rückrufschnittstelle implementiert wird.  
  
 Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar. Der Client sollte Sicherheit eingestellt haben, um sicherzustellen, dass nur Verbindungen zu vertrauensvollen Diensten hergestellt werden.  
  
 Ein Lernprogramm zum Erstellen einer grundlegenden WCF-Dienst und Client finden Sie unter [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### <a name="to-access-a-duplex-service"></a>So greifen Sie auf einen Duplexdienst zu  
  
1.  Erstellen Sie einen Dienst, der zwei Schnittstellen enthält. Die erste Schnittstelle ist dem Dienst vorbehalten, die zweite Schnittstelle wird für den Rückruf verwendet. Weitere Informationen zu einen Duplexdienst zu erstellen, finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Führen Sie den Dienst aus.  
  
3.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Generieren von Datenverträgen (Schnittstellen) für den Client. Informationen hierzu finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
4.  Implementieren Sie die Rückrufschnittstelle in der Client-Klasse, wie im nachfolgenden Beispiel dargestellt.  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse. Der Konstruktor benötigt eine Instanz der Client-Klasse.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Erstellen Sie eine Instanz des WCF-Clients mithilfe des Konstruktors, der erfordert ein <xref:System.ServiceModel.InstanceContext> Objekt. Der zweite Parameter des Konstruktors ist der Name eines Endpunkts in der Konfigurationsdatei.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Rufen Sie die Methoden des WCF-Clients als erforderlich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das Erstellen einer Client-Klasse veranschaulicht, die auf einen Duplexvertrag zugreift.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
  
## <a name="see-also"></a>Siehe auch  
 [Tutorial mit ersten Schritten](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Vorgehensweise: Verwenden von ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
