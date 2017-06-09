---
title: "Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "Duplexverträge [WCF]"
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag
Eine Funktion von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] besteht in der Fähigkeit, einen Dienst zu erstellen, der ein Duplexnachrichtenmuster verwendet.Anhand dieses Musters kann ein Dienst mit dem Client über einen Rückruf kommunizierenDieses Thema beschreibt die Schritte, mit denen Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client in einer Client\-Klasse, die die Rückrufschnittstelle implementiert, erstellen können.  
  
 Eine Dualbindung macht die IP\-Adresse des Clients für den Dienst verfügbar.Der Client sollte Sicherheit eingestellt haben, um sicherzustellen, dass nur Verbindungen zu vertrauensvollen Diensten hergestellt werden.  
  
 Ein Lernprogramm zum Erstellen eines grundlegenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienstes und \- Clients finden Sie im [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### So greifen Sie auf einen Duplexdienst zu  
  
1.  Erstellen Sie einen Dienst, der zwei Schnittstellen enthält.Die erste Schnittstelle ist dem Dienst vorbehalten, die zweite Schnittstelle wird für den Rückruf verwendet.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Erstellen eines Duplexdienstes finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Führen Sie den Dienst aus.  
  
3.  Verwenden Sie das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), um die Verträge \(Schnittstellen\) für den Client zu generieren.Weitere Informationen dazu finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
4.  Implementieren Sie die Rückrufschnittstelle in der Client\-Klasse, wie im nachfolgenden Beispiel dargestellt.  
  
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
  
5.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.InstanceContext>\-Klasse.Der Konstruktor benötigt eine Instanz der Client\-Klasse.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Erstellen Sie eine Instanz des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients mit dem Konstruktor, für den ein <xref:System.ServiceModel.InstanceContext>\-Objekt erforderlich ist.Der zweite Parameter des Konstruktors ist der Name eines Endpunkts in der Konfigurationsdatei.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Rufen Sie die Methoden des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients wie erforderlich auf.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Erstellen einer Client\-Klasse veranschaulicht, die auf einen Duplexvertrag zugreift.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## .NET Framework-Sicherheit  
  
## Siehe auch  
 [Lernprogramm 'Erste Schritte'](../../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Vorgehensweise: Verwenden der ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)