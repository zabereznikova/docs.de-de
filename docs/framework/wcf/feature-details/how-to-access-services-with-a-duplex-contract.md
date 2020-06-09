---
title: 'Vorgehensweise: Zugreifen auf Dienste mit einem Duplex Vertrag'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: bc42792b827b49265a0b1addf959de2fa1a041e3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597214"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Vorgehensweise: Zugreifen auf Dienste mit einem Duplex Vertrag

Eine Funktion von Windows Communication Foundation (WCF) ist die Möglichkeit, einen Dienst zu erstellen, der ein Duplex Nachrichten Muster verwendet. Anhand dieses Musters kann ein Dienst mit dem Client über einen Rückruf kommunizieren In diesem Thema werden die Schritte zum Erstellen eines WCF-Clients in einer Client Klasse gezeigt, die die Rückruf Schnittstelle implementiert.

Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar. Der Client sollte Sicherheit eingestellt haben, um sicherzustellen, dass nur Verbindungen zu vertrauensvollen Diensten hergestellt werden.

Ein Tutorial zum Erstellen eines einfachen WCF-Dienstanbieter und-Clients finden Sie im [Tutorial zu](../getting-started-tutorial.md)den ersten Schritten.

## <a name="to-access-a-duplex-service"></a>So greifen Sie auf einen Duplexdienst zu

1. Erstellen Sie einen Dienst, der zwei Schnittstellen enthält. Die erste Schnittstelle ist dem Dienst vorbehalten, die zweite Schnittstelle wird für den Rückruf verwendet. Weitere Informationen zum Erstellen eines Duplex Dienstanbieter finden [Sie unter Gewusst wie: Erstellen eines Duplex Vertrags](how-to-create-a-duplex-contract.md).

2. Führen Sie den Dienst aus.

3. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um Verträge (Schnittstellen) für den Client zu generieren. Weitere Informationen hierzu finden Sie unter Gewusst [wie: Erstellen eines Clients](../how-to-create-a-wcf-client.md).

4. Implementieren Sie die Rückrufschnittstelle in der Client-Klasse, wie im nachfolgenden Beispiel dargestellt.

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
            Console.WriteLine("Equation({0})", equation)
        End Sub
    End Class
    ```

5. Erstellen Sie eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse. Der Konstruktor benötigt eine Instanz der Client-Klasse.

    ```csharp
    InstanceContext site = new InstanceContext(new CallbackHandler());
    ```

    ```vb
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())
    ```

6. Erstellen Sie eine Instanz des WCF-Clients mithilfe des Konstruktors, für den ein-Objekt erforderlich ist <xref:System.ServiceModel.InstanceContext> . Der zweite Parameter des Konstruktors ist der Name eines Endpunkts in der Konfigurationsdatei.

    ```csharp
    CalculatorDuplexClient wcfClient = new CalculatorDuplexClient(site, "default");
    ```

    ```vb
    Dim wcfClient As New CalculatorDuplexClient(site, "default")
    ```

7. Nennen Sie die Methoden des WCF-Clients nach Bedarf.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird das Erstellen einer Client-Klasse veranschaulicht, die auf einen Duplexvertrag zugreift.

[!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
[!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- [Tutorial zu den ersten Schritten](../getting-started-tutorial.md)
- [Vorgehensweise: Erstellen eines Duplexvertrags](how-to-create-a-duplex-contract.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Vorgehensweise: Erstellen eines Clients](../how-to-create-a-wcf-client.md)
- [Vorgehensweise: Verwenden der ChannelFactory](how-to-use-the-channelfactory.md)
